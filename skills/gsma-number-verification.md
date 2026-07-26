---
name: Verify a mobile number silently, with an SMS OTP fallback
description: Use the GSMA Open Gateway Number Verification API for network-based silent verification of the number on the device, falling back to the One Time Password SMS API where silent authentication is unavailable.
api: openapi/gsma-open-gateway-number-verification-openapi.yml
generated: '2026-07-25'
method: generated
operations:
  - phoneNumberVerify
  - phoneNumberShare
  - sendCode
  - validateCode
---

# Verify a number without asking the user to type anything

## Before you start

Number Verification is the second most widely deployed Open Gateway API (148 launched instances at
last harvest). It only works when the request is made **over the mobile data connection** of the
device being verified — that is what lets the network identify the line. Resolve `{apiRoot}` to the
operator or aggregator serving that subscriber.

Authorization is OpenID Connect. The flow that matters here is usually the authorization-code flow
executed over cellular, or CIBA when the app cannot open a browser: the GSMA sandbox names
`client_credentials`, CIBA, `authorization_code` and `jwt_bearer` as the supported flows, and the
Number Verification specification describes passing a GSMA TS.43 temporary token as
`login_hint=operatortoken:<token>`.

Scopes: `phoneNumberVerify` requires `number-verification:verify`; `phoneNumberShare` requires
`number-verification:device-phone-number:read`.

## Steps

1. **Prefer verify over share.** Call `phoneNumberVerify` with the number you already believe the
   user has. It returns a boolean match and never discloses the number, which is the
   privacy-preserving choice and usually the easier consent conversation.
2. **Use share only when you genuinely do not know the number.** `phoneNumberShare` returns the
   device's phone number itself and needs the stronger scope.
3. **Handle the "not on cellular" case explicitly.** `403
   NUMBER_VERIFICATION.USER_NOT_AUTHENTICATED_BY_MOBILE_NETWORK` means "Client must authenticate via
   the mobile network to use this service" — the user is on Wi-Fi or behind a VPN. This is a normal
   condition, not an error to retry.
4. **Fall back to OTP.** When silent verification is unavailable or the operator has not launched
   it, call `sendCode` on the One Time Password SMS API (scope
   `one-time-password-sms:send-validate`) to send a code, then `validateCode` with the
   `authenticationId` it returned and the code the user typed.
5. **Respect the OTP failure semantics.** `400 ONE_TIME_PASSWORD_SMS.INVALID_OTP` means the code is
   wrong for that `authenticationId`; `400 ONE_TIME_PASSWORD_SMS.VERIFICATION_EXPIRED` means the
   `authenticationId` is dead and you must start a new send;
   `400 ONE_TIME_PASSWORD_SMS.VERIFICATION_FAILED` means the attempt ceiling was reached. Start over
   rather than retrying the same `authenticationId`.

## Errors you must handle

- `403 ONE_TIME_PASSWORD_SMS.MAX_OTP_CODES_EXCEEDED` — too many OTPs for this MSISDN; try later.
- `403 ONE_TIME_PASSWORD_SMS.PHONE_NUMBER_BLOCKED` / `PHONE_NUMBER_NOT_ALLOWED` — the operator will
  not send SMS to this line for business reasons. Do not retry.
- `403 INVALID_TOKEN_CONTEXT` — the number does not match the token context.
- `422 MISSING_IDENTIFIER` / `UNNECESSARY_IDENTIFIER` — you sent no identifier when the token needs
  one, or you sent one when the token already identifies the device.

Full catalog: `errors/gsma-problem-types.yml`.

## Do not

- Do not use `phoneNumberShare` when `phoneNumberVerify` answers the question — you take on a data
  liability you did not need.
- Do not treat OTP as equivalent assurance to network verification; it is the fallback, and the
  specification says so.
- Do not hard-code a base URL: `{apiRoot}` belongs to the operator.
