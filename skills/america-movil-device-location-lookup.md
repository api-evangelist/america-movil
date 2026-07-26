---
name: Look up the network location of a device on the Claro network
description: >-
  Use Claro Brasil's LBS Devices Locations API to retrieve the last known — or
  freshly measured — network-derived location of a mobile line, choosing the
  location method and freshness policy, and reading the three possible geometry
  shapes it can return.
api: openapi/america-movil-claro-device-location-openapi.json
operations:
- device-locations-v1
auth: OAuth 2.0 client credentials (HTTP Basic, HTTP Bearer and X-API-Key also declared)
generated: '2026-07-25'
method: generated
---

# Look up the network location of a device on the Claro network

This is Claro's own Location Based Services API (Apigee proxy
`mobile-lbsdeviceslocations-v1`), not a CAMARA document. It answers with a
geometry and an accuracy shape rather than a yes/no verdict.

## Before you start

- Registered Claro Insight account with this API approved; OAuth 2.0
  client-credentials token from `https://api.claro.com.br/oauth2/v1/token`.
- Base path: `https://api.claro.com.br/mobile/v1` (sandbox
  `https://api-sandbox.claro.com.br/mobile/v1`; on-premises production
  `https://cas.apigw.claro.com.br/mobile/v1` and `https://lpa.apigw.claro.com.br/mobile/v1`).
- This returns precise personal location. Treat consent and retention as the
  first design question, not the last.

## Step 1 — Call the operation

Operation `device-locations-v1`:

```
GET /lbs/devices/locations
Authorization: Bearer <access_token>
X-QueryString: MSISDN=5521912345678&locationMethod=99&locationType=LAST
```

All parameters travel in the single required `X-QueryString` header, which Claro
describes as the LGPD-compliant way to carry the identifiers:

- `MSISDN` (required) — international format, e.g. `5521912345678`.
- `locationMethod` (optional) — `0–99` A-GPS (not currently available),
  `100–499` TA/RTT, `500–999` Cell ID.
- `locationType` (optional) — `CURRENT` forces a live fix, `LAST` reads the last
  stored fix, `CURRENT_OR_LAST` tries live then falls back, `LAST_OR_CURRENT`
  reads stored then tries live.

Choose `LAST` when you only need a coarse recent position — it avoids paging the
network and is faster; choose `CURRENT` only when freshness actually changes the
decision.

## Step 2 — Read the response

Every response carries `apiVersion` and `transactionId` (keep the
`transactionId` — it is the only correlation id Claro gives you for support).
`data.deviceLocation.geograficLocation` arrives in one of three shapes:

- `typeArea: Point` — a single coordinate, with `pointName` naming the CRS.
- `typeArea: CircularArea` — coordinate plus `accuracy.radius` in metres.
- `typeArea: CircularArcArea` — coordinate plus `accuracy.inRadius`,
  `outRadius`, `startAngle`, `stopAngle` (a sector of a cell).

Always read `validationDate` before using the fix: with `LAST` it is the age of a
stored position, which may be old.

## Step 3 — Handle errors

- `422` carries the real story in `error.detailedMessage` — the fourteen
  `API-LBSDEVICESLOCATIONS-001…014` business faults, including unknown subscriber
  (`004`), absent subscriber (`005`), location-server congestion (`006`) and
  network congestion (`013`). Congestion faults are retryable; unknown/absent
  subscriber is not.
- `429 API-LBSDEVICESLOCATIONS-429` means the per-MSISDN request ceiling was hit —
  stop polling that number.
- `451` means the lookup was refused for legal or geographic reasons.
- Full registry: `errors/america-movil-error-codes.yml`.

## Rules that apply to every call

- No idempotency key and no pagination — one call, one fix.
- Billing is per successful query.
- If you need a yes/no "is the device inside this area" answer instead of a
  coordinate, that is a different product (Device Location Verify, which follows
  CAMARA `location.yaml` v0.1.0 and requires documented subject consent).
