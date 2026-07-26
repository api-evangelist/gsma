---
name: Charge a purchase to the mobile bill and refund it
description: Use the GSMA Open Gateway Carrier Billing and Carrier Billing Refund APIs to run a one-step or two-step carrier-billed payment, track it through CloudEvents notifications, and refund it.
api: openapi/gsma-open-gateway-carrier-billing-openapi.yml
generated: '2026-07-25'
method: generated
operations:
  - createPayment
  - preparePayment
  - validatePayment
  - confirmPayment
  - retrievePayment
  - retrievePayments
  - cancelPayment
  - createRefund
  - retrieveRefund
  - retrieveRefunds
  - retrievePaymentRemainingAmount
---

# Carrier-billed payment, end to end

## Before you start

Both Carrier Billing and Carrier Billing Refund are at **work-in-progress** version (`vwip`) on the
GSMA portal — the shapes below can change between CAMARA releases, so pin the spec version you built
against. Resolve `{apiRoot}` to the operator or aggregator; the GSMA charges nobody.

Scopes: `carrier-billing:payments:create`, `carrier-billing:payments:read`,
`carrier-billing:payments:write`, `carrier-billing-refund:refunds:create`,
`carrier-billing-refund:refunds:read`.

Supply a `clientCorrelator` on create. A duplicate is rejected with
`400 INVALID_ARGUMENT — clientCorrelator already exist on server.`, which is your signal that the
first attempt landed. Never re-issue a payment after a timeout without checking first.

## Steps — one-step payment

1. `createPayment` with the amount, currency and the payer's device identifier. If you supplied a
   `sink`, the operator will POST CloudEvents to it:
   `org.camaraproject.carrier-billing.v0.payment-reserved`, `...payment-pending-validation`,
   `...payment-completed`, `...payment-denied`, `...payment-cancelled`.
2. `retrievePayment` to read the current state when you have no sink, or to reconcile.
3. `cancelPayment` while the payment is still cancellable.

## Steps — two-step payment (reserve, then confirm)

1. `preparePayment` to reserve the amount against the subscriber's account.
2. `validatePayment` with the code the user was sent, when the operator requires user validation.
   A wrong code is `400 CARRIER_BILLING.INVALID_CODE`; exhausting the attempts is
   `400 CARRIER_BILLING.VALIDATION_FAILED — the maximum number of attempts have been consumed for
   this validation.`
3. `confirmPayment` to capture. `409 CARRIER_BILLING.PAYMENT_CONFIRMED` means it is already
   captured — that is a success you have already achieved, not a failure to retry.

## Steps — refund

1. `retrievePaymentRemainingAmount` first: it tells you how much of the original payment is still
   refundable, which prevents most refund rejections.
2. `createRefund` for a full or partial refund. Notifications arrive as
   `org.camaraproject.carrier-billing-refund.v0.refund-completed`, `...refund-denied`,
   `...refund-in-bill`.
3. `retrieveRefund` / `retrieveRefunds` to reconcile.

## Errors you must handle

- `403 CARRIER_BILLING.PAYMENT_DENIED` — denied by business rules; do not retry the same request.
- `422 CARRIER_BILLING.UNAUTHORIZED_AMOUNT` — the amount is above what is authorised for this user.
- `422 CARRIER_BILLING.USER_AMOUNT_THRESHOLD_OVERPASSED` — accumulated mobile payments have passed
  the account threshold. Fall back to another payment method; the ceiling will not move on retry.
- `403 CARRIER_BILLING_REFUND.PAYMENT_NOT_ELIGIBLE_FOR_REFUND`, `422
  CARRIER_BILLING_REFUND.INVALID_PAYMENT_STATUS` ("Payment is not yet completed"),
  `422 CARRIER_BILLING_REFUND.REFUND_DETAILS_MISMATCH`,
  `422 CARRIER_BILLING_REFUND.TAXES_MANAGEMENT_MISMATCH` — refund preconditions.
- `400 CARRIER_BILLING.TOO_MANY_MATCHING_RECORDS` on the list operations — narrow the date range.

Full catalog: `errors/gsma-problem-types.yml`. Event surface: `asyncapi/gsma-webhooks.yml`.

## Do not

- Do not retry a create on a network timeout without first reading by `clientCorrelator`. Carrier
  billing has real money consequences and CAMARA gives you a duplicate check, not an
  idempotent replay.
- Do not build against `vwip` shapes without a version pin and a plan to re-test on each CAMARA
  meta-release.
