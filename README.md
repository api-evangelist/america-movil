# América Móvil (america-movil)

América Móvil, S.A.B. de C.V. is the largest telecommunications group in Latin America, headquartered in Mexico City and controlled by the Slim family. It serves roughly 331 million wireless subscribers and 79 million fixed revenue-generating units across 23 countries (2025 Form 20-F), operating as **Telcel** and **Telmex** in its home market of Mexico, as **Claro** across most of Latin America and the Caribbean, and as majority owner of **A1 Telekom Austria Group** in Central and Eastern Europe. It is a mobile network operator and fixed-line carrier — it owns the spectrum, the radio access network, the SIM estate and the subscriber identity records that network APIs monetize.

Its API posture is the classic carrier posture. There is **no corporate developer portal**: `americamovil.com` is an investor-relations site, and `developer.`, `developers.`, `docs.`, `api.` and `opengateway.` subdomains do not resolve. The only real API surface in the group belongs to one operating company — **Claro Brasil**, whose *Claro Insight* marketplace publishes a 14-API catalog with plans and a checkout flow, but keeps every Swagger download behind registration.

In **Mexico**, América Móvil's home and largest market, Telcel launched GSMA Open Gateway on 28 May 2025 alongside Altán Redes, AT&T Mexico and Telefónica Mexico with SIM Swap, Number Verification and Device Location. It publishes no portal, no specification and no sandbox — only a business sales contact form. That is a commitment and a sales listing, not a callable API.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/america-movil/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/america-movil/refs/heads/main/apis.yml)

## CAMARA and GSMA Open Gateway posture

- **GSMA Open Gateway participant:** yes. Claro launched in Brazil (Nov 2023, with TIM and Vivo), Telcel in Mexico (28 May 2025), and Claro is named in the Argentina and Uruguay launches.
- **CAMARA implementation:** real in Brazil only. Claro Brasil's SIM Swap API ships a downloadable OpenAPI 3.0.3 document with CAMARA's `retrieve-date` / `check` operation shape, live sandbox and production hosts under a `/gsma/gateway/` path, and OAuth2 client credentials. Everywhere else — including Mexico — CAMARA is a press release with nothing callable behind it.
- **CAMARA project membership:** no. América Móvil is not among the companies named in the Linux Foundation's February 2022 CAMARA founding announcement. It is a downstream implementer, not a specification author.
- **Aduna:** not an equity partner. América Móvil was named at Ericsson's September 2024 launch of the network-API joint venture but is **absent** from the twelve-CSP equity structure completed in July 2025 — leaving the largest operator group in Latin America outside the industry's biggest commercial aggregation channel.
- **Channel to developers:** aggregator-mediated. Infobip carries Claro's CAMARA-compliant network APIs in Brazil; Brazil launch materials point developers at Microsoft Azure and integrators. In Mexico there is no direct developer channel at all.
- **TM Forum:** no Open API conformance certification found anywhere in the group.
- **3GPP exposure:** no NEF/SCEF surface, no network-slicing API, no edge/MEC API published.

## Auth

Both harvested specifications use **OAuth 2.0 client credentials** (`tokenUrl /oauth2/v1/token`); the Device Location spec additionally declares HTTP Basic, HTTP Bearer and an `X-API-Key` header. **CIBA does not appear anywhere** — there is no backchannel authentication, no OIDC configuration and no subject-consent mechanism in evidence. `https://api.claro.com.br/oauth2/v1/token` is live and returns 401 to anonymous callers.

## Tags

- Telecommunications
- Mexico
- Latin America
- Mobile Network Operator
- Network APIs
- CAMARA
- Open Gateway
- SIM Swap
- Identity Verification
- Device Location
- Broadband
- 5G
- Carrier

## Timestamps

- **Created:** 2026-07-25
- **Modified:** 2026-07-25

## APIs

### Claro SIM Swap API

CAMARA-aligned SIM Swap API from Claro Brasil. Returns the date of the most recent SIM pairing change on a Brazilian mobile line, or checks whether a swap occurred within a caller-supplied window.

- **Human URL:** [https://www.claroinsight.com.br/pt-br/sim-swap](https://www.claroinsight.com.br/pt-br/sim-swap)
- **Base URL:** `https://api.claro.com.br/mobile/v1/gsma/gateway/simswap`
- **OpenAPI:** [openapi/america-movil-claro-sim-swap-openapi.json](openapi/america-movil-claro-sim-swap-openapi.json) — OpenAPI 3.0.3, `POST /retrieve-date`, `POST /check`

### Claro Device Location API

"Mobile - LBS Devices Locations" (Apigee proxy `mobile-lbsdeviceslocations-v1`) — the last known network-derived location of a device on the Claro network.

- **Human URL:** [https://www.claroinsight.com.br/pt-br/device-location-retrievel](https://www.claroinsight.com.br/pt-br/device-location-retrievel)
- **Base URL:** `https://api.claro.com.br/mobile/v1`
- **OpenAPI:** [openapi/america-movil-claro-device-location-openapi.json](openapi/america-movil-claro-device-location-openapi.json) — OpenAPI 3.0.0, `GET /lbs/devices/locations`

### Claro Insight catalog (documentation gated behind registration)

| API | Page |
| --- | --- |
| Claro Number Verification | [/pt-br/number-verification](https://www.claroinsight.com.br/pt-br/number-verification) |
| Claro Device Location Verify | [/pt-br/device-location-verify](https://www.claroinsight.com.br/pt-br/device-location-verify) |
| Claro Know Your Customer | [/pt-br/claro-kyc](https://www.claroinsight.com.br/pt-br/claro-kyc) |
| Claro KYC Fill In | [/pt-br/fill-in](https://www.claroinsight.com.br/pt-br/fill-in) |
| Claro Number Recycling | [/pt-br/number-recycling](https://www.claroinsight.com.br/pt-br/number-recycling) |
| Claro Tenure | [/pt-br/tenure](https://www.claroinsight.com.br/pt-br/tenure) |
| Claro Geofencing | [/pt-br/geofencing](https://www.claroinsight.com.br/pt-br/geofencing) |
| Claro Face Match | [/pt-br/facial-biometrics](https://www.claroinsight.com.br/pt-br/facial-biometrics) |
| Claro Alerta | [/pt-br/claro-alerta](https://www.claroinsight.com.br/pt-br/claro-alerta) |
| Claro Valida Telefone | [/pt-br/claro-valida-telefone](https://www.claroinsight.com.br/pt-br/claro-valida-telefone) |
| Claro Valida Endereço 2.0 | [/pt-br/claro-valida-endereco-v2](https://www.claroinsight.com.br/pt-br/claro-valida-endereco-v2) |
| Claro Score | [/pt-br/claro-score](https://www.claroinsight.com.br/pt-br/claro-score) |

### Telcel Mobile Authentication APIs (Mexico)

Number Verification, SIM change detection and device location verification, marketed by Telcel to enterprises under GSMA Open Gateway. **No developer portal, no specification, no sandbox, no self-serve signup** — a sales contact form only.

- **Human URL:** [https://www.telcel.com/empresas/soluciones/busines-intelligence/autenticacion-movil](https://www.telcel.com/empresas/soluciones/busines-intelligence/autenticacion-movil)

## Links

- [América Móvil](https://www.americamovil.com/)
- [Telcel](https://www.telcel.com/)
- [Claro Brasil](https://www.claro.com.br/)
- [Claro Insight API catalog](https://www.claroinsight.com.br/pt-br/catalogo-api)
- [Claro Insight registration](https://www.claroinsight.com.br/user/register)
- [CAMARA Project](https://camaraproject.org/)
- [GSMA Open Gateway](https://www.gsma.com/solutions-and-impact/gsma-open-gateway/)

## Review

See [review.yml](review.yml) for the full API Evangelist reviewer finding — probe-by-probe HTTP statuses, spec provenance, CAMARA evidence strength per API, Open Gateway and Aduna posture, auth model, and the honest absence of TM Forum conformance, 3GPP exposure, webhooks, SDKs and public source control.
