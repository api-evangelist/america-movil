---
name: Check a Brazilian mobile line for a recent SIM swap
description: >-
  Use Claro Brasil's CAMARA-derived SIM Swap API to decide whether a phone number
  can still be trusted as an authentication factor, either by reading the date of
  the last SIM pairing change or by asking a yes/no question over a time window.
api: openapi/america-movil-claro-sim-swap-openapi.json
operations:
- retrieveSimSwapDate
- checkSimSwap
auth: OAuth 2.0 client credentials
generated: '2026-07-25'
method: generated
---

# Check a Brazilian mobile line for a recent SIM swap

Claro Brasil exposes SIM Swap as two operations on one base path. Both take a
single MSISDN and return a fraud signal — nothing is created or changed.

## Before you start

- You need a registered Claro Insight account with the SIM Swap API approved, and
  the `client_id` / `client_secret` issued to it. There is no anonymous access and
  no public test credential.
- Only Brazilian Claro lines resolve. An unknown number returns
  `404 SIM_SWAP.UNKNOWN_PHONE_NUMBER`, which is a legitimate answer, not an error
  to retry.
- Base path: `https://api.claro.com.br/mobile/v1/gsma/gateway/simswap`
  (sandbox: `https://api-sandbox.claro.com.br/...`).

## Step 1 — Get an access token

```
POST https://api.claro.com.br/oauth2/v1/token
Content-Type: application/x-www-form-urlencoded
Authorization: Basic base64(client_id:client_secret)

grant_type=client_credentials
```

Read `access_token` from the JSON response. Older Claro services expect the same
credential in an `x-client-auth` header instead of `Authorization`; SIM Swap uses
the standard header.

## Step 2 — Ask the right question

**When did the SIM last change?** — `retrieveSimSwapDate`

```
POST /retrieve-date
Authorization: Bearer <access_token>
Content-Type: application/json

{ "phoneNumber": "+5511999999999" }
```

Returns `{ "latestSimChange": "<date-time>" }`. Use this when you want to score
the age of the pairing yourself.

**Did a swap happen in the last N hours?** — `checkSimSwap`

```
POST /check
Authorization: Bearer <access_token>
Content-Type: application/json

{ "phoneNumber": "+5511999999999", "maxAge": 240 }
```

`maxAge` is in hours, 1–2400, default 240 (ten days). Returns
`{ "swapped": true|false }`. Prefer this when your policy is a simple threshold —
it keeps the personal data you handle to a single boolean.

## Step 3 — Handle the answers

| Status | Code | What to do |
|---|---|---|
| 200 | — | Apply your policy. `swapped: true` or a recent `latestSimChange` means do not use SMS OTP on this line. |
| 400 | `INVALID_ARGUMENT` | Fix the payload; `phoneNumber` must match `^\+?[0-9]{5,15}$`. Do not retry unchanged. |
| 401 | `UNAUTHENTICATED` | Token missing or expired — repeat step 1. |
| 403 | `PERMISSION_DENIED` | The API or version is not contracted for your client, or your source IP is not allow-listed. |
| 404 | `SIM_SWAP.UNKNOWN_PHONE_NUMBER` | Not a Claro line. Fall back to another signal; this is not a failure. |
| 409 | `CONFLICT` | Another request is already in flight for this MSISDN. Serialize per number and retry after it completes. |
| 429 | — | You exceeded the contracted request policy. Back off. |
| 500 / 503 / 504 | `INTERNAL` / `UNAVAILABLE` / `TIMEOUT` | Retry with backoff; repeated 504s mean you should simplify the request. |

## Rules that apply to every call

- **No idempotency key exists.** Retrying a POST re-runs the lookup and re-bills
  it; the 409 conflict is the only in-flight protection. See
  `conventions/america-movil-conventions.yml`.
- **Billing is per successful query.** A resolved true/false counts.
- **The result is personal data under LGPD.** Log the verdict, not the payload,
  and keep the retention justified by the fraud decision you made.
- **Do not treat SIM Swap as an authentication step on its own** — it is a signal
  that feeds a decision, per the GSMA Mobile Connect Account Takeover Protection
  model this API derives from.
