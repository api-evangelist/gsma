# GSMA (gsma)

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

The GSMA (GSM Association) is the London-headquartered global trade body for the mobile industry, representing roughly 750 mobile network operators and around 400 companies in the wider mobile ecosystem, and the organiser of MWC Barcelona. In telecom's API value chain the GSMA is not a network operator and not an aggregator; it is the standards and commitment layer. Its GSMA Open Gateway initiative is the memorandum of understanding under which 69 operator groups, representing 78% of global mobile connections, commit to exposing a common set of network APIs, while the API specifications themselves are authored in the Linux Foundation's CAMARA project. The GSMA's API posture is unusually open for a standards body: its Open Gateway developer portal at open-gateway.gsma.com publishes 17 CAMARA OpenAPI 3.0.3 documents in full, without login, alongside a live public deployment map covering 607 launched API instances across 80 operators and 65 countries, and it runs a separate, fully open Mobile Money API developer portal with a downloadable OpenAPI 3.0.0 specification, SDKs, and use-case guides. The gates are real but narrow: the API sandbox requires a GitHub sign-in, the anti-fraud Scam Signal API is held in a private GSMA repository rather than in public CAMARA, and the commercial GSMA Services products (Device Check, IMEI Database, PathFinder, Disposable Number Check) are membership and contract gated with no public documentation. The GSMA runs no production network API endpoints of its own — every Open Gateway API is served by an operator or a channel partner such as Infobip, IPification, TMT iD, XConnect, or Singtel.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/gsma/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/gsma/refs/heads/main/apis.yml)

## Tags

- Telecommunications
- United Kingdom
- Standards
- Trade Association
- Network APIs
- CAMARA
- Open Gateway
- Mobile Network Operators
- Identity Verification
- SIM Swap
- Mobile Money
- eSIM
- 5G
- Anti-Fraud
- Specification

## Timestamps

- **Created:** 2026-07-25
- **Modified:** 2026-07-25

## Developer Portals

The GSMA runs two first-party developer surfaces, both readable without an account:

- **GSMA Open Gateway** — [https://open-gateway.gsma.com/](https://open-gateway.gsma.com/) (HTTP 200). Documentation for 17 CAMARA network APIs at [/docs](https://open-gateway.gsma.com/docs), a live [API deployment map](https://open-gateway.gsma.com/map), and a CAMARA-compliant [sandbox](https://open-gateway.gsma.com/sandbox) behind a GitHub sign-in.
- **GSMA Mobile Money API** — [https://developer.mobilemoneyapi.io/](https://developer.mobilemoneyapi.io/) (HTTP 200). The Mobile Money API specification, a downloadable OpenAPI 3.0.0 document, security guidelines, and five language SDK guides.

The corporate site at [gsma.com](https://www.gsma.com/solutions-and-impact/gsma-open-gateway/) is the marketing and commitment layer; its API descriptions page defers every technical description to [camaraproject.org](https://camaraproject.org/api-overview).

## CAMARA and Open Gateway posture

The GSMA is the convener, not an implementer. GSMA Open Gateway is the memorandum of understanding under which **69 operator groups representing 78% of global mobile connections** commit to exposing a common set of network APIs; the specifications themselves are authored in the Linux Foundation's CAMARA project. The GSMA runs no production network API endpoint of its own — every Open Gateway API instance is served by an operator or a channel partner.

The GSMA's own public deployment feed (`assets-map-launches.json`, generated 2026-07-25) records **607 launched API instances across 80 operators and 65 countries, 135 of them certified**. SIM Swap (205) and Number Verification (148) dominate. Named channel partners in the feed: Enstream, IDlayr, Infobip, IPification, JT Global, M1, Openxpand, Singtel, TMT iD, XConnect.

**What is open versus gated.** Seventeen complete CAMARA OpenAPI 3.0.3 documents are published anonymously on the GSMA portal, plus the Mobile Money OpenAPI 3.0.0 — that is genuinely open for a standards body. The gates are narrow and specific: the sandbox needs a GitHub sign-in, the anti-fraud **Scam Signal** API is deliberately held in a *private* GSMA repository rather than public CAMARA, the commercial GSMA Services catalogue (Device Check, IMEI Database, PathFinder, Disposable Number Check) is contract-gated with no public API documentation, and GSMA Intelligence sits behind a sign-in wall. GSMA's own GitHub organisation holds two repositories, both front-end web utilities, and zero OpenAPI.

**Authorization.** Every harvested Open Gateway spec declares a single `openId` OpenID Connect security scheme with per-operation CAMARA scopes. **CIBA is real here, not aspirational** — the sandbox names it as a supported flow, the Number Verification spec uses it to carry GSMA TS.43 temporary tokens, and 94 live deployments in GSMA's own feed declare a CIBA flow (57 certified). Client Credentials (256), Authorization Code (190), and JWT Bearer (7) make up the rest.

**Not a TM Forum conformance holder.** The GSMA operates no BSS/OSS and publishes no TMF620/TMF622/TMF641 implementation; TM Forum lists CAMARA as an ODA partner, which is an alignment between bodies rather than a GSMA certification. Likewise there is no GSMA NEF or SCEF — CAMARA is the northbound abstraction that operators map onto their own 3GPP exposure.

## APIs

### GSMA Mobile Money API

The GSMA Mobile Money API is a harmonised REST/JSON specification for mobile money platforms, developed by the GSMA with the mobile money industry and published openly at developer.mobilemoneyapi.io. Version 1.2.0 defines 53 paths across Transactions, Quotations, Accounts, Bills, Debit Mandates, Links, and Authorisation Codes, covering merchant payments, disbursements, international transfers, P2P transfers, recurring payments, account linking, bill payments, and agent cash-in/cash-out. The OpenAPI 3.0.0 document is downloadable without registration; the simulator sandbox host referenced in the spec did not resolve in DNS on the review date.

- **Human URL:** [https://developer.mobilemoneyapi.io/api-versions-1.2/](https://developer.mobilemoneyapi.io/api-versions-1.2/)

#### Tags

- Mobile Money
- Payments
- Financial Inclusion
- Specification

#### Properties

- [OpenAPI](openapi/gsma-mobile-money-api-openapi.yml)
- [Documentation](https://developer.mobilemoneyapi.io/)
- [APIReference](https://developer.mobilemoneyapi.io/api-versions-1.2/resources/api-service-definition.html)
- [Documentation](https://developer.mobilemoneyapi.io/api-versions-1.2/resources/open-oas3-ui.html)
- [Documentation](https://developer.mobilemoneyapi.io/sdks/getting-started/introduction.html)
- [Documentation](https://developer.mobilemoneyapi.io/security/)
- [Documentation](https://developer.mobilemoneyapi.io/guidelines/)

### GSMA Open Gateway Call Forwarding Signal API

CAMARA Call Forwarding Signal API as published on the GSMA Open Gateway developer portal. Lets an application check whether unconditional or conditional call forwarding is active on a subscriber's line, a common indicator of an in-progress scam. Operators expose the endpoints; GSMA publishes the specification and documentation. OpenAPI 3.0.3, version 0.2.0, 2 path(s) and 2 operation(s); authorization is OpenID Connect (openIdConnect security scheme) with per-operation CAMARA scopes.

- **Human URL:** [https://open-gateway.gsma.com/docs/call-forwarding-signal](https://open-gateway.gsma.com/docs/call-forwarding-signal)

#### Tags

- Anti-Fraud
- Call Forwarding
- CAMARA
- Open Gateway
- Network APIs

#### Properties

- [OpenAPI](openapi/gsma-open-gateway-call-forwarding-signal-openapi.yml)
- [Documentation](https://open-gateway.gsma.com/docs/call-forwarding-signal)
- [APIReference](https://open-gateway.gsma.com/docs/call-forwarding-signal/api-reference)
- [Documentation](https://open-gateway.gsma.com/docs)
- [Sandbox](https://open-gateway.gsma.com/sandbox)

### GSMA Open Gateway Carrier Billing API

CAMARA Carrier Billing API as published on the GSMA Open Gateway developer portal. Allows a service provider to charge a purchase to the end user's mobile account through the operator, with payment creation, confirmation, and status retrieval. Specification is at work-in-progress version on the GSMA portal. OpenAPI 3.0.3, version wip, 6 path(s) and 7 operation(s); authorization is OpenID Connect (openIdConnect security scheme) with per-operation CAMARA scopes.

- **Human URL:** [https://open-gateway.gsma.com/docs/carrier-billing](https://open-gateway.gsma.com/docs/carrier-billing)

#### Tags

- Payments
- Carrier Billing
- CAMARA
- Open Gateway
- Network APIs

#### Properties

- [OpenAPI](openapi/gsma-open-gateway-carrier-billing-openapi.yml)
- [Documentation](https://open-gateway.gsma.com/docs/carrier-billing)
- [APIReference](https://open-gateway.gsma.com/docs/carrier-billing/api-reference)
- [Documentation](https://open-gateway.gsma.com/docs)
- [Sandbox](https://open-gateway.gsma.com/sandbox)

### GSMA Open Gateway Carrier Billing Refund API

CAMARA Carrier Billing Refund API as published on the GSMA Open Gateway developer portal. Companion to Carrier Billing, allowing full or partial refunds of a carrier-billed payment to be requested and tracked. Specification is at work-in-progress version on the GSMA portal. OpenAPI 3.0.3, version wip, 3 path(s) and 4 operation(s); authorization is OpenID Connect (openIdConnect security scheme) with per-operation CAMARA scopes.

- **Human URL:** [https://open-gateway.gsma.com/docs/carrier-billing-refund](https://open-gateway.gsma.com/docs/carrier-billing-refund)

#### Tags

- Payments
- Carrier Billing
- Refunds
- CAMARA
- Open Gateway
- Network APIs

#### Properties

- [OpenAPI](openapi/gsma-open-gateway-carrier-billing-refund-openapi.yml)
- [Documentation](https://open-gateway.gsma.com/docs/carrier-billing-refund)
- [APIReference](https://open-gateway.gsma.com/docs/carrier-billing-refund/api-reference)
- [Documentation](https://open-gateway.gsma.com/docs)
- [Sandbox](https://open-gateway.gsma.com/sandbox)

### GSMA Open Gateway Mobile Device Identifier API

CAMARA Mobile Device Identifier API as published on the GSMA Open Gateway developer portal. Returns identifying details for the device a subscriber is currently using, such as manufacturer, model, and type allocation code, retrieved from the operator network rather than the handset. OpenAPI 3.0.3, version 0.2.0, 2 path(s) and 2 operation(s); authorization is OpenID Connect (openIdConnect security scheme) with per-operation CAMARA scopes.

- **Human URL:** [https://open-gateway.gsma.com/docs/device-identifier](https://open-gateway.gsma.com/docs/device-identifier)

#### Tags

- Device Information
- IMEI
- CAMARA
- Open Gateway
- Network APIs

#### Properties

- [OpenAPI](openapi/gsma-open-gateway-device-identifier-openapi.yml)
- [Documentation](https://open-gateway.gsma.com/docs/device-identifier)
- [APIReference](https://open-gateway.gsma.com/docs/device-identifier/api-reference)
- [Documentation](https://open-gateway.gsma.com/docs)
- [Sandbox](https://open-gateway.gsma.com/sandbox)

### GSMA Open Gateway Device Location Retrieval API

CAMARA Device Location Retrieval API as published on the GSMA Open Gateway developer portal. Retrieves the network-derived location of a device as a circle or polygon with an accuracy radius, without relying on handset GPS. Specification is at work-in-progress version on the GSMA portal. OpenAPI 3.0.3, version wip, 1 path(s) and 1 operation(s); authorization is OpenID Connect (openIdConnect security scheme) with per-operation CAMARA scopes.

- **Human URL:** [https://open-gateway.gsma.com/docs/device-location-retrieval](https://open-gateway.gsma.com/docs/device-location-retrieval)

#### Tags

- Location
- Device Location
- CAMARA
- Open Gateway
- Network APIs

#### Properties

- [OpenAPI](openapi/gsma-open-gateway-device-location-retrieval-openapi.yml)
- [Documentation](https://open-gateway.gsma.com/docs/device-location-retrieval)
- [APIReference](https://open-gateway.gsma.com/docs/device-location-retrieval/api-reference)
- [Documentation](https://open-gateway.gsma.com/docs)
- [Sandbox](https://open-gateway.gsma.com/sandbox)

### GSMA Open Gateway Device Location Verification API

CAMARA Device Location Verification API as published on the GSMA Open Gateway developer portal. Answers whether a device is within a requested area rather than returning coordinates, a privacy-preserving pattern widely used for transaction-risk checks. Specification is at work-in-progress version on the GSMA portal. OpenAPI 3.0.3, version wip, 1 path(s) and 1 operation(s); authorization is OpenID Connect (openIdConnect security scheme) with per-operation CAMARA scopes.

- **Human URL:** [https://open-gateway.gsma.com/docs/device-location-verification](https://open-gateway.gsma.com/docs/device-location-verification)

#### Tags

- Location
- Device Location
- Anti-Fraud
- CAMARA
- Open Gateway
- Network APIs

#### Properties

- [OpenAPI](openapi/gsma-open-gateway-device-location-verification-openapi.yml)
- [Documentation](https://open-gateway.gsma.com/docs/device-location-verification)
- [APIReference](https://open-gateway.gsma.com/docs/device-location-verification/api-reference)
- [Documentation](https://open-gateway.gsma.com/docs)
- [Sandbox](https://open-gateway.gsma.com/sandbox)

### GSMA Open Gateway Device Reachability Status API

CAMARA Device Reachability Status API as published on the GSMA Open Gateway developer portal. Reports whether a device is currently reachable on the network and by which connectivity type, used for IoT fleet monitoring and delivery decisions. OpenAPI 3.0.3, version 0.6.1, 1 path(s) and 1 operation(s); authorization is OpenID Connect (openIdConnect security scheme) with per-operation CAMARA scopes.

- **Human URL:** [https://open-gateway.gsma.com/docs/device-reachability-status](https://open-gateway.gsma.com/docs/device-reachability-status)

#### Tags

- Device Status
- IoT
- CAMARA
- Open Gateway
- Network APIs

#### Properties

- [OpenAPI](openapi/gsma-open-gateway-device-reachability-status-openapi.yml)
- [Documentation](https://open-gateway.gsma.com/docs/device-reachability-status)
- [APIReference](https://open-gateway.gsma.com/docs/device-reachability-status/api-reference)
- [Documentation](https://open-gateway.gsma.com/docs)
- [Sandbox](https://open-gateway.gsma.com/sandbox)

### GSMA Open Gateway Device Roaming Status API

CAMARA Device Roaming Status API as published on the GSMA Open Gateway developer portal. Reports whether a subscriber's device is currently roaming and, where available, the visited country, used for fraud scoring and travel-aware experiences. OpenAPI 3.0.3, version 0.6.1, 1 path(s) and 1 operation(s); authorization is OpenID Connect (openIdConnect security scheme) with per-operation CAMARA scopes.

- **Human URL:** [https://open-gateway.gsma.com/docs/device-roaming-status](https://open-gateway.gsma.com/docs/device-roaming-status)

#### Tags

- Device Status
- Roaming
- CAMARA
- Open Gateway
- Network APIs

#### Properties

- [OpenAPI](openapi/gsma-open-gateway-device-roaming-status-openapi.yml)
- [Documentation](https://open-gateway.gsma.com/docs/device-roaming-status)
- [APIReference](https://open-gateway.gsma.com/docs/device-roaming-status/api-reference)
- [Documentation](https://open-gateway.gsma.com/docs)
- [Sandbox](https://open-gateway.gsma.com/sandbox)

### GSMA Open Gateway Device Swap API

CAMARA Device Swap API as published on the GSMA Open Gateway developer portal. Checks whether the device associated with a mobile number has changed within a recent window, a signal used alongside SIM Swap to detect account-takeover attempts. OpenAPI 3.0.3, version 0.2.0, 2 path(s) and 2 operation(s); authorization is OpenID Connect (openIdConnect security scheme) with per-operation CAMARA scopes.

- **Human URL:** [https://open-gateway.gsma.com/docs/device-swap](https://open-gateway.gsma.com/docs/device-swap)

#### Tags

- Anti-Fraud
- Device Swap
- CAMARA
- Open Gateway
- Network APIs

#### Properties

- [OpenAPI](openapi/gsma-open-gateway-device-swap-openapi.yml)
- [Documentation](https://open-gateway.gsma.com/docs/device-swap)
- [APIReference](https://open-gateway.gsma.com/docs/device-swap/api-reference)
- [Documentation](https://open-gateway.gsma.com/docs)
- [Sandbox](https://open-gateway.gsma.com/sandbox)

### GSMA Open Gateway Home Devices QoD API

CAMARA Home Devices Quality on Demand API as published on the GSMA Open Gateway developer portal. Requests a prioritised quality-of-service profile for a device on a fixed or home broadband connection rather than a mobile connection. OpenAPI 3.0.3, version 0.4.0, 1 path(s) and 1 operation(s); authorization is OpenID Connect (openIdConnect security scheme) with per-operation CAMARA scopes.

- **Human URL:** [https://open-gateway.gsma.com/docs/home-devices-quality-on-demand](https://open-gateway.gsma.com/docs/home-devices-quality-on-demand)

#### Tags

- Quality on Demand
- Broadband
- CAMARA
- Open Gateway
- Network APIs

#### Properties

- [OpenAPI](openapi/gsma-open-gateway-home-devices-quality-on-demand-openapi.yml)
- [Documentation](https://open-gateway.gsma.com/docs/home-devices-quality-on-demand)
- [APIReference](https://open-gateway.gsma.com/docs/home-devices-quality-on-demand/api-reference)
- [Documentation](https://open-gateway.gsma.com/docs)
- [Sandbox](https://open-gateway.gsma.com/sandbox)

### GSMA Open Gateway Know Your Customer Match API

CAMARA Know Your Customer Match API as published on the GSMA Open Gateway developer portal. Submits customer-supplied identity attributes such as name, address, and date of birth and returns per-attribute match results against the operator's subscriber record, without exposing the operator data itself. OpenAPI 3.0.3, version 0.3.0, 1 path(s) and 1 operation(s); authorization is OpenID Connect (openIdConnect security scheme) with per-operation CAMARA scopes.

- **Human URL:** [https://open-gateway.gsma.com/docs/know-your-customer](https://open-gateway.gsma.com/docs/know-your-customer)

#### Tags

- Identity Verification
- KYC
- CAMARA
- Open Gateway
- Network APIs

#### Properties

- [OpenAPI](openapi/gsma-open-gateway-know-your-customer-openapi.yml)
- [Documentation](https://open-gateway.gsma.com/docs/know-your-customer)
- [APIReference](https://open-gateway.gsma.com/docs/know-your-customer/api-reference)
- [Documentation](https://open-gateway.gsma.com/docs)
- [Sandbox](https://open-gateway.gsma.com/sandbox)

### GSMA Open Gateway Number Verification API

CAMARA Number Verification API as published on the GSMA Open Gateway developer portal. Silently verifies or retrieves the mobile number of the device making a request using network-based or SIM-based authentication, with single-use short-lived tokens and no refresh tokens. This is the most widely deployed Open Gateway API after SIM Swap. OpenAPI 3.0.3, version wip, 2 path(s) and 2 operation(s); authorization is OpenID Connect (openIdConnect security scheme) with per-operation CAMARA scopes.

- **Human URL:** [https://open-gateway.gsma.com/docs/number-verification](https://open-gateway.gsma.com/docs/number-verification)

#### Tags

- Identity Verification
- Number Verification
- CAMARA
- Open Gateway
- Network APIs

#### Properties

- [OpenAPI](openapi/gsma-open-gateway-number-verification-openapi.yml)
- [Documentation](https://open-gateway.gsma.com/docs/number-verification)
- [APIReference](https://open-gateway.gsma.com/docs/number-verification/api-reference)
- [Documentation](https://open-gateway.gsma.com/docs)
- [Sandbox](https://open-gateway.gsma.com/sandbox)

### GSMA Open Gateway One Time Password SMS API

CAMARA One Time Password SMS API as published on the GSMA Open Gateway developer portal. Sends a one-time password by SMS through the operator and validates the code the user returns, offered as a fallback where silent network authentication is unavailable. OpenAPI 3.0.3, version 1.0.0, 2 path(s) and 2 operation(s); authorization is OpenID Connect (openIdConnect security scheme) with per-operation CAMARA scopes.

- **Human URL:** [https://open-gateway.gsma.com/docs/otp-validation](https://open-gateway.gsma.com/docs/otp-validation)

#### Tags

- Authentication
- OTP
- SMS
- CAMARA
- Open Gateway
- Network APIs

#### Properties

- [OpenAPI](openapi/gsma-open-gateway-otp-validation-openapi.yml)
- [Documentation](https://open-gateway.gsma.com/docs/otp-validation)
- [APIReference](https://open-gateway.gsma.com/docs/otp-validation/api-reference)
- [Documentation](https://open-gateway.gsma.com/docs)
- [Sandbox](https://open-gateway.gsma.com/sandbox)

### GSMA Open Gateway Population Density Data API

CAMARA Population Density Data API as published on the GSMA Open Gateway developer portal. Returns aggregated, anonymised estimates of device density across a requested geographic area and time window, delivered asynchronously with callback notifications. OpenAPI 3.0.3, version 0.2.0, 1 path(s) and 1 operation(s); authorization is OpenID Connect (openIdConnect security scheme) with per-operation CAMARA scopes.

- **Human URL:** [https://open-gateway.gsma.com/docs/population-density-data](https://open-gateway.gsma.com/docs/population-density-data)

#### Tags

- Analytics
- Population Density
- CAMARA
- Open Gateway
- Network APIs

#### Properties

- [OpenAPI](openapi/gsma-open-gateway-population-density-data-openapi.yml)
- [Documentation](https://open-gateway.gsma.com/docs/population-density-data)
- [APIReference](https://open-gateway.gsma.com/docs/population-density-data/api-reference)
- [Documentation](https://open-gateway.gsma.com/docs)
- [Sandbox](https://open-gateway.gsma.com/sandbox)

### GSMA Open Gateway Quality On Demand API

CAMARA Quality on Demand API as published on the GSMA Open Gateway developer portal. Requests, extends, and releases a prioritised network quality profile for a device session, with event notifications when a session changes state. This is the flagship programmable-network API of the Open Gateway programme. OpenAPI 3.0.3, version 0.11.1, 4 path(s) and 5 operation(s); authorization is OpenID Connect (openIdConnect security scheme) with per-operation CAMARA scopes.

- **Human URL:** [https://open-gateway.gsma.com/docs/quality-on-demand](https://open-gateway.gsma.com/docs/quality-on-demand)

#### Tags

- Quality on Demand
- 5G
- Network Slicing
- CAMARA
- Open Gateway
- Network APIs

#### Properties

- [OpenAPI](openapi/gsma-open-gateway-quality-on-demand-openapi.yml)
- [Documentation](https://open-gateway.gsma.com/docs/quality-on-demand)
- [APIReference](https://open-gateway.gsma.com/docs/quality-on-demand/api-reference)
- [Documentation](https://open-gateway.gsma.com/docs)
- [Sandbox](https://open-gateway.gsma.com/sandbox)

### GSMA Open Gateway SIM Swap API

CAMARA SIM Swap API as published on the GSMA Open Gateway developer portal. Checks whether the SIM associated with a mobile number has been swapped within a recent window and returns the last swap date, the single most widely deployed Open Gateway API worldwide. Specification is at work-in-progress version on the GSMA portal. OpenAPI 3.0.3, version wip, 2 path(s) and 2 operation(s); authorization is OpenID Connect (openIdConnect security scheme) with per-operation CAMARA scopes.

- **Human URL:** [https://open-gateway.gsma.com/docs/sim-swap](https://open-gateway.gsma.com/docs/sim-swap)

#### Tags

- Anti-Fraud
- SIM Swap
- CAMARA
- Open Gateway
- Network APIs

#### Properties

- [OpenAPI](openapi/gsma-open-gateway-sim-swap-openapi.yml)
- [Documentation](https://open-gateway.gsma.com/docs/sim-swap)
- [APIReference](https://open-gateway.gsma.com/docs/sim-swap/api-reference)
- [Documentation](https://open-gateway.gsma.com/docs)
- [Sandbox](https://open-gateway.gsma.com/sandbox)

### GSMA Open Gateway Simple Edge Discovery API

CAMARA Simple Edge Discovery API as published on the GSMA Open Gateway developer portal. Returns the closest edge cloud zone to a given device so an application can route traffic to the lowest-latency multi-access edge computing deployment. OpenAPI 3.0.3, version 1.0.0, 1 path(s) and 1 operation(s); authorization is OpenID Connect (openIdConnect security scheme) with per-operation CAMARA scopes.

- **Human URL:** [https://open-gateway.gsma.com/docs/simple-edge-discovery](https://open-gateway.gsma.com/docs/simple-edge-discovery)

#### Tags

- Edge Computing
- MEC
- CAMARA
- Open Gateway
- Network APIs

#### Properties

- [OpenAPI](openapi/gsma-open-gateway-simple-edge-discovery-openapi.yml)
- [Documentation](https://open-gateway.gsma.com/docs/simple-edge-discovery)
- [APIReference](https://open-gateway.gsma.com/docs/simple-edge-discovery/api-reference)
- [Documentation](https://open-gateway.gsma.com/docs)
- [Sandbox](https://open-gateway.gsma.com/sandbox)

## Common Properties

- [Website](https://www.gsma.com/)
- [DeveloperPortal](https://open-gateway.gsma.com/)
- [Documentation](https://open-gateway.gsma.com/docs)
- [Sandbox](https://open-gateway.gsma.com/sandbox)
- [Documentation](https://developer.mobilemoneyapi.io/)
- [Documentation](https://www.gsma.com/solutions-and-impact/gsma-open-gateway/gsma-open-gateway-api-descriptions/)
- [Documentation](https://www.gsma.com/solutions-and-impact/gsma-open-gateway/gsma-open-gateway-frequently-asked-questions/)
- [Documentation](https://www.gsma.com/solutions-and-impact/gsma-open-gateway/supporters/)
- [Dataset](https://d3bj8knxlstxyw.cloudfront.net/assets-map-launches.json)
- [Documentation](https://open-gateway.gsma.com/map)
- [Specification](https://camaraproject.org/api-overview)
- [GitHubOrganization](https://github.com/GSMA)
- [GitHubOrganization](https://github.com/camaraproject)
- [LinkedIn](https://www.linkedin.com/company/gsma/)
- [Twitter](https://twitter.com/gsma)
- [YouTube](https://www.youtube.com/gsma)
- [Newsroom](https://www.gsma.com/newsroom/)
- [Services](https://www.gsmaservices.com/)
- [Membership](https://www.gsma.com/get-involved/gsma-membership/)

## Maintainers

- Kin Lane <kin@apievangelist.com>
