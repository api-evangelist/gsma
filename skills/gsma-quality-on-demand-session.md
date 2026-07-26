---
name: Request and manage a prioritised network quality session
description: Use the GSMA Open Gateway Quality on Demand API to request a prioritised QoS profile for a device session, extend it, watch its state via CloudEvents notifications, and release it.
api: openapi/gsma-open-gateway-quality-on-demand-openapi.yml
generated: '2026-07-25'
method: generated
operations:
  - createSession
  - getSession
  - extendQosSessionDuration
  - retrieveSessionsByDevice
  - deleteSession
  - postNotification
---

# Take a QoS session, hold it, then give it back

## Before you start

Quality on Demand (spec version 0.11.1) is the flagship programmable-network API of the Open Gateway
programme. Resolve `{apiRoot}` to the operator serving the device; the GSMA runs no QoD endpoint.
Authorization is OpenID Connect with these scopes:

| Operation | Scope |
|---|---|
| `createSession` | `quality-on-demand:sessions:create` |
| `getSession` | `quality-on-demand:sessions:read` |
| `retrieveSessionsByDevice` | `quality-on-demand:sessions:retrieve-by-device` |
| `extendQosSessionDuration` | `quality-on-demand:sessions:update` |
| `deleteSession` | `quality-on-demand:sessions:delete` |

QoS profiles are operator-defined. Ask the operator which profiles exist before you request one —
the API will not enumerate an arbitrary catalogue for you.

## Steps

1. **Create the session.** `createSession` takes the device identifier, the QoS profile name, a
   duration, and optionally `sink` + `sinkCredential` for notifications. Supply a `clientCorrelator`
   you generate: it is the closest thing CAMARA has to an idempotency key, and resubmitting the same
   one is rejected with `400 INVALID_ARGUMENT — clientCorrelator already exist on server.` Treat
   that rejection as "my earlier request landed", then read the session rather than creating another.
2. **Subscribe to state changes rather than polling.** If you passed a `sink`, the operator POSTs a
   CloudEvent of type `org.camaraproject.quality-on-demand.v0.qos-status-changed` to it, secured
   with the `notificationsBearerAuth` bearer credential you supplied in `sinkCredential`. Validate
   that credential on receipt; the sink is your endpoint, so its security is your responsibility.
3. **Read state when you must.** `getSession` returns the current `qosStatus`. Use
   `retrieveSessionsByDevice` to find sessions you have lost track of for a given device.
4. **Extend rather than recreate.** `extendQosSessionDuration` adds time to a running session.
   Extension is state-dependent: `409 QUALITY_ON_DEMAND.SESSION_EXTENSION_NOT_ALLOWED` means the
   session is not in a state that allows it. Read the session, then decide.
5. **Always release.** `deleteSession` ends the session. A session you forget is capacity the
   operator has reserved and, in most commercial arrangements, capacity you are paying for.

## Errors you must handle

- `400 QUALITY_ON_DEMAND.DURATION_OUT_OF_RANGE` — the requested duration is outside the allowed
  range for that QoS profile.
- `400 INVALID_SINK` — the sink URL is not valid for the specified protocol.
- `403 PERMISSION_DENIED` / `INVALID_TOKEN_CONTEXT` — scope or token-context mismatch.
- `422 UNIDENTIFIABLE_DEVICE` / `UNSUPPORTED_DEVICE_IDENTIFIERS` — the device cannot be identified,
  or none of the identifiers you sent is supported by this implementation.
- `429 TOO_MANY_REQUESTS` — back off; no numeric limit is published by the GSMA.
- `503 UNAVAILABLE`, `504 TIMEOUT` — retry with backoff; a QoS request that times out may still have
  created a session, so read by `clientCorrelator`/device before retrying blind.

Full catalog: `errors/gsma-problem-types.yml`. Event surface: `asyncapi/gsma-webhooks.yml`.

## Related

For a fixed/home broadband connection rather than a mobile one, use the Home Devices QoD API
(`setQos`, scope `home-devices-qod`), which has its own conflict codes:
`HOME_DEVICES_QOD.QOS_TOO_HIGH`, `HOME_DEVICES_QOD.ROUTER_OFFLINE`,
`HOME_DEVICES_QOD.NOT_CONNECTED_TO_REQUIRED_INTERFACE`, `HOME_DEVICES_QOD.TOO_MANY_DEVICES`.
