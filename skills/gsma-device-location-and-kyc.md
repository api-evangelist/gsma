---
name: Verify where a device is and whether the identity behind it matches
description: Use the GSMA Open Gateway location and KYC APIs to answer a privacy-preserving "is this device in this area?" question and to match customer-supplied identity attributes against the operator's subscriber record.
api: openapi/gsma-open-gateway-device-location-verification-openapi.yml
generated: '2026-07-25'
method: generated
operations:
  - verifyLocation
  - retrieveLocation
  - KYC_Match
  - getRoamingStatus
  - getReachabilityStatus
---

# Ask the narrowest question the network can answer

## Before you start

Resolve `{apiRoot}` to the operator serving the subscriber. Authorization is OpenID Connect with:

| Operation | Scope |
|---|---|
| `verifyLocation` | `location-verification:verify` |
| `retrieveLocation` | `location-retrieval:read` |
| `KYC_Match` | `kyc-match:match` |
| `getRoamingStatus` | `device-roaming-status:read` |
| `getReachabilityStatus` | `device-reachability-status:read` |

Location Verification and Location Retrieval are both at work-in-progress version (`vwip`) on the
GSMA portal.

## Steps

1. **Verify, do not retrieve.** `verifyLocation` answers whether the device is inside an area you
   supply and returns a match verdict with a freshness indication — it does not return coordinates.
   This is the pattern to use for transaction-risk checks, and the one that survives a privacy
   review.
2. **Retrieve only with a reason.** `retrieveLocation` returns the network-derived location as a
   circle or polygon with an accuracy radius. Use it when your use case genuinely needs a position,
   and record why.
3. **Set `maxAge` honestly.** Both operations take a freshness bound. If the network cannot meet it
   you get `422 LOCATION_RETRIEVAL.UNABLE_TO_FULFILL_MAX_AGE` (or the
   `LOCATION_VERIFICATION.` equivalent) rather than a stale answer. Widen the bound rather than
   treating the error as a failure.
4. **Match identity without reading it.** `KYC_Match` takes the attributes the customer gave you
   (name, address, date of birth, id document) and returns per-attribute match results. The operator
   record is never exposed to you — you learn only whether each attribute agrees.
5. **Add context signals.** `getRoamingStatus` tells you whether the line is roaming (and where, if
   published); `getReachabilityStatus` tells you whether the device is reachable and over which
   connectivity type. Both are cheap and useful as corroboration.

## Errors you must handle

- `422 LOCATION_VERIFICATION.AREA_NOT_COVERED` — the operator cannot cover the requested area.
- `422 LOCATION_VERIFICATION.INVALID_AREA` — the area is too small to answer meaningfully.
- `422 LOCATION_RETRIEVAL.UNABLE_TO_LOCATE` / `LOCATION_VERIFICATION.UNABLE_TO_LOCATE` — the network
  cannot locate the device right now.
- `403 KNOW_YOUR_CUSTOMER.ID_DOCUMENT_REQUIRED` / `ID_DOCUMENT_MISMATCH` — the id document is
  required to validate the properties, or does not match the one held against the phone number.
- `400 KNOW_YOUR_CUSTOMER.INVALID_PARAM_COMBINATION` — the attribute combination is not accepted.
- `422 UNABLE_TO_PROVIDE_ROAMING_STATUS` / `UNABLE_TO_PROVIDE_REACHABILITY_STATUS` — network issue.
- `422 MISSING_IDENTIFIER` / `UNNECESSARY_IDENTIFIER` — identifier and token context disagree.

Full catalog: `errors/gsma-problem-types.yml`.

## Do not

- Do not call `retrieveLocation` when `verifyLocation` answers your question.
- Do not treat a `422` freshness or coverage error as a fraud signal — it is a capability limit.
- Do not hard-code a base URL; check https://open-gateway.gsma.com/map for who has launched what.
