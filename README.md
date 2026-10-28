# América Móvil

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

América Móvil, S.A.B. de C.V. is the largest telecommunications group in Latin America, headquartered in Mexico City and controlled by the Slim family. It serves roughly 331 million wireless subscribers and 79 million fixed revenue-generating units across 23 countries (2025 Form 20-F), operating as Telcel and Telmex in its home market of Mexico, as Claro across most of Latin America and the Caribbean, and as the majority owner of A1 Telekom Austria Group in Central and Eastern Europe. In the value chain it is a mobile network operator and fixed-line carrier — it owns the spectrum, the radio access network, the SIM estate and the subscriber identity records that network APIs monetize, and it does not resell anyone else's connectivity. Its API posture is the classic carrier posture: there is no corporate developer portal at americamovil.com (the domain is an investor-relations site and returns 403 to non-browser clients; developer.*, developers.*, docs.*, api.* and opengateway.* subdomains do not resolve), and the only real API surface in the group sits inside one operating company — Claro Brasil's "Claro Insight" marketplace at claroinsight.com.br, a registration-gated catalog of 14 network and identity APIs including CAMARA-aligned SIM Swap, Number Verification and Device Location. In Mexico, Telcel launched GSMA Open Gateway on 28 May 2025 alongside Altán Redes, AT&T Mexico and Telefónica Mexico with three APIs — SIM Swap, Number Verification and Device Location — but publishes no portal, no specification and no sandbox, only a business sales contact form. América Móvil is a GSMA Open Gateway participant and was named in Ericsson's September 2024 launch of the Aduna network-API joint venture, but it is absent from the final twelve-CSP equity structure completed in July 2025; in Brazil its CAMARA APIs reach developers through the CPaaS aggregator Infobip. Outside the Brazilian marketplace, América Móvil is partner-gated and sales-led, and is reachable by most developers only through an aggregator rather than directly.

**Areas:** Telecommunications · Mexico · Latin America · Mobile Network Operator · Network APIs · CAMARA · Open Gateway · SIM Swap · Identity Verification · Device Location · Broadband · 5G

## América Móvil on APIs.io

Everything profiled for América Móvil is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/america-movil/](https://apis.io/providers/america-movil/)** — or go straight to one of the APIs or properties below.

### APIs (16)

- [Claro Number Verification API](https://apis.io/apis/america-movil/claro-number-verification-api/) — CAMARA-aligned Number Verification API from Claro Brasil — silent verification that a mobile number is the one actually attached to the device making the…
- [Claro Know Your Customer API](https://apis.io/apis/america-movil/claro-know-your-customer-api/) — KYC Match-style API from Claro Brasil that validates user-supplied identity attributes — phone number, name, address, e-mail — against Claro's subscriber…
- [Claro KYC Fill In API](https://apis.io/apis/america-movil/claro-kyc-fill-in-api/) — Returns verified customer registration data held by Claro Brasil so that onboarding forms can be pre-populated from carrier records rather than…
- [Claro Number Recycling API](https://apis.io/apis/america-movil/claro-number-recycling-api/) — Detects whether a Brazilian mobile number has changed owner — the recycling of a disconnected number to a new subscriber — so that accounts keyed to a phone…
- [Claro Tenure API](https://apis.io/apis/america-movil/claro-tenure-api/) — Reports how long a mobile number has been active on the Claro Brasil network and the plan associated with it, used as a stability and risk signal in…
- [Claro Geofencing API](https://apis.io/apis/america-movil/claro-geofencing-api/) — Monitors M2M/IoT devices on the Claro Brasil network against geographic fences and raises cellular-network notifications when a device enters or leaves an…
- [Claro Face Match API](https://apis.io/apis/america-movil/claro-face-match-api/) — Biometric face-match validation against Claro Brasil's own image records, sold as an identity-assurance step alongside the network APIs. Listed in the Claro…
- [Claro Alerta API](https://apis.io/apis/america-movil/claro-alerta-api/) — Detects SIM-card or handset changes on a Claro Brasil mobile line and raises an alert, a Claro-branded companion to the CAMARA SIM Swap API. Listed in the…
- [Claro Valida Telefone API](https://apis.io/apis/america-movil/claro-valida-telefone-api/) — Validates the relationship between a Brazilian CPF (taxpayer identifier) and a mobile number using Claro Brasil subscriber records. Listed in the Claro…
- [Claro Valida Endereço 2.0 API](https://apis.io/apis/america-movil/claro-valida-endereco-api/) — Scores a declared address against antenna-proximity analysis of the Claro Brasil network, used to corroborate residential address claims during onboarding.…
- [Claro Score API](https://apis.io/apis/america-movil/claro-score-api/) — Credit-risk scoring derived from Claro Brasil telecom behaviour, used to identify lower-risk consumers. Listed in the Claro Insight catalog; documentation…
- [Telcel Mobile Authentication APIs](https://apis.io/apis/america-movil/telcel-mobile-authentication-apis/) — América Móvil's GSMA Open Gateway surface in its home market of Mexico, marketed by Telcel to enterprises as "Autenticación Móvil" — Number Verification…
- [América Móvil Check SIM swap API](https://apis.io/apis/america-movil/america-movil-check-sim-swap-api/) — The Check SIM swap API from América Móvil — 1 operation(s) for check sim swap.
- [América Móvil Device Locations API](https://apis.io/apis/america-movil/america-movil-device-locations-api/) — The Device Locations API from América Móvil — 1 operation(s) for device locations.
- [América Móvil Location verification API](https://apis.io/apis/america-movil/america-movil-location-verification-api/) — The Location verification API from América Móvil — 1 operation(s) for location verification.
- [América Móvil Retrieve SIM swap date API](https://apis.io/apis/america-movil/america-movil-retrieve-sim-swap-date-api/) — The Retrieve SIM swap date API from América Móvil — 1 operation(s) for retrieve sim swap date.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### Arazzo workflows (1)

Multi-step workflows that chain operations into a business task.

- [Account-takeover check for a Brazilian mobile line](https://apis.io/arazzos/america-movil/america-movil-account-takeover-check/)

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [America Movil Webhooks](https://apis.io/asyncapis/america-movil/america-movil-webhooks/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [america-movil-claro](https://apis.io/servers/america-movil/america-movil-claro/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [America Movil Agentic Access](https://apis.io/agentic-access/america-movil/america-movil-agentic-access/)

#### Collections (2)

Postman and Open Collection request collections.

- [Mobile - LBS Devices Locations\n (Proxy Apigee: mobile-lbsdeviceslocations-v1)](https://apis.io/collections/america-movil/open-america-movil-claro-device-location/)
- [SIM Swap](https://apis.io/collections/america-movil/open-america-movil-claro-sim-swap/)

#### Overlays (2)

OpenAPI overlays, including conversational phrasing for each operation.

- [America Movil Claro Device Location Overlay](https://apis.io/overlays/america-movil/america-movil-claro-device-location-overlay/)
- [America Movil Claro Sim Swap Overlay](https://apis.io/overlays/america-movil/america-movil-claro-sim-swap-overlay/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [America Movil Authentication](https://apis.io/security/america-movil/america-movil-authentication/)
- [America Movil Domain Security](https://apis.io/security/america-movil/america-movil-domain-security/)

#### OAuth scopes (1)

The permissions the API asks for.

- [America Movil Scopes](https://apis.io/scopes/america-movil/america-movil-scopes/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [America Movil Plans](https://apis.io/plans/america-movil/america-movil-plans/)

#### Rate limits (1)

Published request limits.

- [America Movil Rate Limits](https://apis.io/rate-limits/america-movil/america-movil-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.americamovil.com/)
- [Documentation](https://www.claroinsight.com.br/pt-br/catalogo-api)
- [API reference](https://www.claroinsight.com.br/pt-br/catalogo-api)
- [Sign up](https://www.claroinsight.com.br/user/register)
- [Support](https://www.claroinsight.com.br/pt-br/contato)
- [Blog](https://www.claro.com.br/blog)
- [Privacy policy](https://www.claro.com.br/privacidade)

## API Evangelist rating

**Kin Score 55.7** — strong · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 69.6 |
| Contract quality | 56.5 |
| Contract governance | 18.2 |
| Operational transparency | 55.3 |
| Developer ergonomics | 54.2 |
| Access clarity | 44.7 |

**Agent readiness 35.4** — agent-ready

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | negotiable (partial credit) |
| Idempotency | — |
| Error Semantics | documented (partial credit) |
| OpenAPI Examples | partial |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | yes |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | documented (partial credit) |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | na |
| Operation Distinctiveness | na |

**Regulatory alignment 43.3** — Telecommunications

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/america-movil/](https://apis.io/providers/america-movil/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for América Móvil: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/america-movil/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
