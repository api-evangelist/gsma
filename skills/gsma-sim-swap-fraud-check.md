---
name: Check a subscriber line for SIM-swap and device-swap fraud signals
description: Use the GSMA Open Gateway anti-fraud APIs (CAMARA SIM Swap, Device Swap, Call Forwarding Signal) to score the risk that a mobile number has been taken over, before allowing a high-value action.
api: openapi/gsma-open-gateway-sim-swap-openapi.yml
generated: '2026-07-25'
method: generated
operations:
  - checkSimSwap
  - retrieveSimSwapDate
  - checkDeviceSwap
  - retrieveDeviceSwapDate
  - retrieveUnconditionalCallForwarding
  - retrieveCallForwarding
---

# Check a line for takeover signals

## Before you start

The GSMA hosts none of these endpoints. Resolve the `{apiRoot}` server variable to the operator or
aggregator that serves the subscriber's network — the deployment map at
https://open-gateway.gsma.com/map (JSON at https://d3bj8knxlstxyw.cloudfront.net/assets-map-launches.json)
lists which operator has launched which API in which country. SIM Swap is the most widely deployed
Open Gateway API (205 launched instances at last harvest); Device Swap and Call Forwarding Signal are
much rarer, so check availability before you depend on them.

Authorization is OpenID Connect against **the operator's** authorization server, not the GSMA's. Get
a token carrying the scope the operation declares:

| Operation | Scope |
|---|---|
| `checkSimSwap` | `sim-swap:check` |
| `retrieveSimSwapDate` | `sim-swap:retrieve-date` |
| `checkDeviceSwap` | `device-swap:check` |
| `retrieveDeviceSwapDate` | `device-swap:retrieve-date` |
| `retrieveUnconditionalCallForwarding` | `call-forwarding-signal:unconditional-call-forwardings:read` |
| `retrieveCallForwarding` | `call-forwarding-signal:call-forwardings:read` |

Send `x-correlator` on every request and log the value returned on the response — it is the only
tracing handle across the operator boundary.

## Steps

1. **Ask the cheap yes/no question first.** Call `checkSimSwap` with the `phoneNumber` and a
   `maxAge` (hours) window that matches your risk policy. It returns a boolean, not a date, so it is
   the answer to give a fraud engine. If your access token already identifies the device (a
   three-legged token), do **not** also send `phoneNumber` — the API answers `422
   UNNECESSARY_IDENTIFIER`.
2. **Only escalate to the date when you need it.** `retrieveSimSwapDate` returns the last swap
   timestamp and usually requires a broader consent posture. Treat a `null` date as "no swap on
   record", not as "no data".
3. **Add the device signal.** `checkDeviceSwap` answers the same shape of question for a handset
   change; `retrieveDeviceSwapDate` returns the timestamp. A SIM swap plus a device swap inside the
   same window is a much stronger takeover signal than either alone.
4. **Check for call diversion.** `retrieveUnconditionalCallForwarding` tells you whether calls are
   being unconditionally diverted — a classic in-progress social-engineering indicator. Use
   `retrieveCallForwarding` when you need the conditional forwarding detail too.
5. **Combine, then decide.** These APIs return signals, not verdicts. Score them together with your
   own account signals; do not block solely on a single boolean.

## Errors you must handle

The envelope is `{status, code, message}` as `application/json` — **not** RFC 9457 problem+json.

- `401 UNAUTHENTICATED` / `AUTHENTICATION_REQUIRED` — token missing or expired; re-authenticate.
- `403 INVALID_TOKEN_CONTEXT` — `phoneNumber` is not consistent with the access token. Never retry
  with a different number on the same token.
- `403 PERMISSION_DENIED` — the scope is not granted for this client.
- `404 IDENTIFIER_NOT_FOUND` — the phone number is not on this operator's network. Route to the
  correct operator rather than retrying.
- `422 SERVICE_NOT_APPLICABLE` / `UNSUPPORTED_IDENTIFIER` — the operator does not offer this check
  for this line; fall back to another signal.
- `429 TOO_MANY_REQUESTS` / `QUOTA_EXCEEDED` — rate or quota limit. No numeric limit is published by
  the GSMA; the operator sets it. Back off exponentially.

Full catalog: `errors/gsma-problem-types.yml`.

## Do not

- Do not hard-code a base URL. There is no GSMA endpoint; `{apiRoot}` defaults in the published
  specs (`http://localhost:9091`, `https://example.com:443`) are placeholders.
- Do not treat the CAMARA `openIdConnectUrl` in the spec
  (`https://example.com/.well-known/openid-configuration`) as a real issuer.
- Do not assume a swap check is available everywhere — coverage is per operator, per country.
