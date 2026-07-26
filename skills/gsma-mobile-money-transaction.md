---
name: Run a mobile money transaction with correlation-id idempotency
description: Use the GSMA Mobile Money API to quote, create and reconcile a mobile money transaction using the asynchronous call-back flow, the X-CorrelationID idempotency contract, and the polling fallback.
api: openapi/gsma-mobile-money-api-openapi.yml
generated: '2026-07-25'
method: generated
operations:
  - quotationsPOST
  - quotationsQuotationReferenceGET
  - transactionstypetransactionTypePUT
  - transactionsTransactionReferenceGET
  - transactionsTransactionReferenceReversalsPOST
  - requeststatesServerCorrelationIdGET
  - responsesClientCorrelationIdGET
  - accountsIdentifierTypeIdentifierBalanceGET
---

# Move money, exactly once

## Before you start

This is a different programme from Open Gateway with different conventions. The specification
(OpenAPI 3.0.0, version 1.2.0, 53 paths) declares **no** `securitySchemes` block; credentials travel
as headers:

- `X-API-Key` and `X-Client-Id` — pre-shared client credentials.
- `X-User-Bearer` — the end user's access token when OAuth 2.0 / OIDC is used for end-user
  authentication.
- `X-Content-Hash` — SHA-256 hex digest of the request content, for basic integrity checking.
- `X-Date` — when the message was originated; used to reject stale requests.
- `X-Channel` — the origination channel (USSD, Web, App).

The base URL belongs to the mobile money provider you are integrating with. The simulator host in
the spec's `servers` block, `https://sandbox.mobilemoneyapi.io/simulator/v1.2/passthrough/mm`, did
not resolve in DNS on the harvest date — do not treat it as a working sandbox without checking.

## The idempotency contract — read this before writing any create

The GSMA Mobile Money API Guidelines are explicit:

- The client **must** generate a client correlation id (a UUID) and send it as `X-CorrelationID` on
  the initial request.
- The provider **must** store it so the client can retrieve the result if the call-back is missed.
- When resending a **creation** request, send the **same** `X-CorrelationID`. If the first request
  was processed, the provider rejects the resend as a duplicate (`errorCategory: duplicateRequest`).
- When resending an **update** request, the correlation id is not mandatory: "all update requests
  are idempotent."

That is the whole safety story. Generate the UUID before the first attempt, persist it with your
own transaction record, and reuse it for every retry of that same intent.

## Steps

1. **Quote first when the price is not fixed.** `quotationsPOST` creates a quotation;
   `quotationsQuotationReferenceGET` reads it back. Use the returned quotation on the transaction.
2. **Check funds if the flow needs it.** `accountsIdentifierTypeIdentifierBalanceGET` returns the
   balance for an account addressed by identifier type and identifier (for example MSISDN).
3. **Create the transaction.** `transactionstypetransactionTypePUT` (`POST
   /transactions/type/{transactionType}`) is the current create operation. Send `X-CorrelationID`
   and `X-Callback-URL`. Note that the bare `POST /transactions` operation
   (`transactionsPOST`) is **deprecated** in 1.2.0 and marked for removal — do not build on it.
4. **Receive the result.** The provider PUTs the completed transaction — or the error object — to
   your `X-Callback-URL`. This is the only flow in which you are notified.
5. **Fall back to polling when you have no call-back sink.** The create response carries a
   `serverCorrelationId`; poll `requeststatesServerCorrelationIdGET`
   (`GET /requeststates/{serverCorrelationId}`) until the request state resolves.
6. **Recover a missed call-back.** `responsesClientCorrelationIdGET`
   (`GET /responses/{clientCorrelationId}`) returns the stored response for the correlation id you
   sent. This is the recovery path the guidelines are built around — use it instead of resending.
7. **Read the final record.** `transactionsTransactionReferenceGET` returns the transaction.
8. **Reverse rather than re-create when something is wrong.**
   `transactionsTransactionReferenceReversalsPOST` creates a reversal against the transaction
   reference.

## Errors you must handle

The error object is `{errorCategory, errorCode, errorDescription, errorDateTime, errorParameters}`
— not RFC 9457 problem+json. Categories include `duplicateRequest`; codes include
`insufficientFunds`, `incorrectState`, `maxBalanceExceeded`, `samePartiesError`,
`greaterThanTransactionMaxValue`, `underPaymentNotAllowed`. See
`errors/gsma-problem-types.yml` for the full enum.

## Pagination

List operations use `limit` (default 50) and `offset`, filtered by `fromDateTime` / `toDateTime`,
and return `X-Records-Available-Count` and `X-Records-Returned-Count`.

## Do not

- Do not generate a fresh `X-CorrelationID` on retry of a create — that is how you double-spend.
- Do not use the deprecated `POST /transactions` or the deprecated `requestingLei` /
  `receivingLei` fields.
- Do not assume the simulator host is live.
