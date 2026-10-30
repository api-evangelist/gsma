# GSMA

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

**Areas:** Telecommunications · United Kingdom · Standards · Trade Association · Network APIs · CAMARA · Open Gateway · Mobile Network Operators · Identity Verification · SIM Swap · Mobile Money · eSIM

## GSMA on APIs.io

Everything profiled for GSMA is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/gsma/](https://apis.io/providers/gsma/)** — or go straight to one of the APIs or properties below.

### APIs (41)

- [GSMA Accounts API](https://apis.io/apis/gsma/gsma-accounts-api/) — The **Accounts** APIs are used to support a range of operations on a financial account resource and associated resources. Types of accounts include mobile…
- [GSMA Authorisation Codes API](https://apis.io/apis/gsma/gsma-authorisation-codes-api/) — The **Authorisation** Codes APIs allow a payer to generate a payment code which when presented to the payee, can be redeemed for an amount associated with…
- [GSMA Bills API](https://apis.io/apis/gsma/gsma-bills-api/) — The **Bills** APIs allow a mobile money provider to allow customers to retrieve and pay bills. Specific use cases include: - Retrieving information on…
- [GSMA Call Forwarding information retrieval API](https://apis.io/apis/gsma/gsma-call-forwarding-information-retrieval-api/) — Provides information on Call Forwarding settings for the provided phone number (PhoneNumber).
- [GSMA Check Device Swap API](https://apis.io/apis/gsma/gsma-check-device-swap-api/) — Validate if the SIM of the end-user has been installed in a different device during a past period
- [GSMA Debit Mandates API](https://apis.io/apis/gsma/gsma-debit-mandates-api/) — The **Debit Mandates** APIs allow a mobile money customer to provide prior approval for payments to be taken from their account by a requesting payee. If…
- [GSMA Discovery API](https://apis.io/apis/gsma/gsma-discovery-api/) — Find the closest Edge Cloud Zone to the user device.
- [GSMA Home Devices QoD API](https://apis.io/apis/gsma/gsma-home-devices-qod-api/) — QoD control operations for home devices
- [GSMA Links API](https://apis.io/apis/gsma/gsma-links-api/) — The **Links** APIs are used to establish a link between two separate accounts on the client and provider systems. The API can be used for example to link a…
- [GSMA Location Retrieval API](https://apis.io/apis/gsma/gsma-location-retrieval-api/) — Retrieve the location of a device
- [GSMA Match API](https://apis.io/apis/gsma/gsma-match-api/) — Operations to match a customer identity against the account data bound to their phone number.
- [GSMA One Step Payment API](https://apis.io/apis/gsma/gsma-one-step-payment-api/) — Operations to manage One Step Payment procedure
- [GSMA OTP Management API](https://apis.io/apis/gsma/gsma-otp-management-api/) — API operations to manage OTP codes
- [GSMA Payment API](https://apis.io/apis/gsma/gsma-payment-api/) — Operations to obtain information about payments
- [GSMA Phone Number Share API](https://apis.io/apis/gsma/gsma-phone-number-share-api/) — API operation to return the phone number associated to the access token.
- [GSMA Phone Number Verify API](https://apis.io/apis/gsma/gsma-phone-number-verify-api/) — API operation to verify a phone number received as input. It can be received either in plain text or hashed format.
- [GSMA QoS Sessions API](https://apis.io/apis/gsma/gsma-qos-sessions-api/) — Manage QoS sessions
- [GSMA Quotations API](https://apis.io/apis/gsma/gsma-quotations-api/) — The **Quotations** APIs are used to obtain one or multiple quotes for a mobile money customer who wishes to transfer money. The creation of a quote involves…
- [GSMA Refund API](https://apis.io/apis/gsma/gsma-refund-api/) — Operations to manage Refund procedure
- [GSMA Retrieve Device Swap Date API](https://apis.io/apis/gsma/gsma-retrieve-device-swap-date-api/) — Receive the last date in which the device of the end-user was swapped
- [GSMA Supporting API](https://apis.io/apis/gsma/gsma-supporting-api/) — Supporting APIs consist of the following: - **Heartbeat API:** Used for monitoring purposes and establishes whether the system of an API provider is in a…
- [GSMA Transactions API](https://apis.io/apis/gsma/gsma-transactions-api/) — The **Transactions** APIs are used to support mobile money financial transaction use cases. Transactions are used for a wide range of use cases including…
- [GSMA Two Step Payment API](https://apis.io/apis/gsma/gsma-two-step-payment-api/) — Operations to manage Two Step Payment procedure
- [GSMA Unconditional Call Forwarding information retrieval API](https://apis.io/apis/gsma/gsma-unconditional-call-forwarding-information-retrieval-api/) — Provides information on Unconditional Call Forwarding settings for the provided phone number (PhoneNumber)
- [GSMA Camara Project Scam Signal API](https://apis.io/apis/gsma/scam-signal-api/) — Scam Signal API allows businesses to protect their customers from impersonation scams, particularly Authorized Pushed Payment (APP) fraud.
- [GSMA Api Product API](https://apis.io/apis/gsma/gsma-api-product-api/) — Operations for ApiProduct Resource
- [GSMA API Product Order API](https://apis.io/apis/gsma/gsma-apiproductorder-api/) — Operations for ApiProductOrder Resource
- [GSMA Application API](https://apis.io/apis/gsma/gsma-application-api/) — Application and Application Instance Lice Cycle Management
- [GSMA Application Profiles API](https://apis.io/apis/gsma/gsma-application-profiles-api/) — Operations to define, read and manage an application's thresholds for network quality (latency, jitter, loss, throughput)
- [GSMA Application Owner API](https://apis.io/apis/gsma/gsma-applicationowner-api/) — Operations for ApplicationOwner Resource
- [GSMA Check Subscriber Tenure API](https://apis.io/apis/gsma/gsma-check-subscriber-tenure-api/) — Check details about the length of tenure of the subscriber
- [GSMA Connectivity Insights Subscriptions API](https://apis.io/apis/gsma/gsma-connectivity-insights-subscriptions-api/) — Create and manage a subscription to receive periodic connectivity insights
- [GSMA events subscription API](https://apis.io/apis/gsma/gsma-events-subscription-api/) — Endpoints to register and terminate an Event Listener
- [GSMA Get Device Identifiers API](https://apis.io/apis/gsma/gsma-get-device-identifiers-api/) — Retrieve details about the device being used by a mobile subscriber
- [GSMA Monitor API](https://apis.io/apis/gsma/gsma-monitor-api/) — Operations for Monitor Resource
- [GSMA Network Quality API](https://apis.io/apis/gsma/gsma-network-quality-api/) — Read the network's level of confidence that it can meet the quality thresholds for a given application profile and end user device.
- [GSMA notification listener API](https://apis.io/apis/gsma/gsma-notification-listener-api/) — Notifications for Resource Lifecycle and event notifications
- [GSMA QoS Profiles API](https://apis.io/apis/gsma/gsma-qos-profiles-api/) — Manage QoS Profiles
- [GSMA Send SMS API](https://apis.io/apis/gsma/gsma-send-sms-api/) — The Send SMS API from GSMA — 1 operation(s) for send sms.
- [GSMA Traffic Influence API Read API](https://apis.io/apis/gsma/gsma-traffic-influence-api-read-api/) — Reads existing TrafficInfluence resources
- [GSMA Traffic Influence API Write API](https://apis.io/apis/gsma/gsma-traffic-influence-api-write-api/) — Creates of modifies a TrafficInfluence resource

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Gsma Webhooks](https://apis.io/asyncapis/gsma/gsma-webhooks/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [gsma](https://apis.io/servers/gsma/gsma/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Gsma Agentic Access](https://apis.io/agentic-access/gsma/gsma-agentic-access/)

#### Collections (18)

Postman and Open Collection request collections.

- [Mobile Money API](https://apis.io/collections/gsma/open-gsma-mobile-money-api/)
- [Call Forwarding Signal](https://apis.io/collections/gsma/open-gsma-open-gateway-call-forwarding-signal/)
- [Carrier Billing](https://apis.io/collections/gsma/open-gsma-open-gateway-carrier-billing/)
- [Carrier Billing Refund](https://apis.io/collections/gsma/open-gsma-open-gateway-carrier-billing-refund/)
- [CAMARA Mobile Device Identifier](https://apis.io/collections/gsma/open-gsma-open-gateway-device-identifier/)
- [Device Location Retrieval](https://apis.io/collections/gsma/open-gsma-open-gateway-device-location-retrieval/)
- [Device Location Verification](https://apis.io/collections/gsma/open-gsma-open-gateway-device-location-verification/)
- [Device Reachability Status](https://apis.io/collections/gsma/open-gsma-open-gateway-device-reachability-status/)
- [Device Roaming Status](https://apis.io/collections/gsma/open-gsma-open-gateway-device-roaming-status/)
- [Device Swap](https://apis.io/collections/gsma/open-gsma-open-gateway-device-swap/)
- [Home Devices QoD](https://apis.io/collections/gsma/open-gsma-open-gateway-home-devices-quality-on-demand/)
- [Know Your Customer Match](https://apis.io/collections/gsma/open-gsma-open-gateway-know-your-customer/)
- [Number Verification](https://apis.io/collections/gsma/open-gsma-open-gateway-number-verification/)
- [One Time Password SMS](https://apis.io/collections/gsma/open-gsma-open-gateway-otp-validation/)
- [Population Density Data](https://apis.io/collections/gsma/open-gsma-open-gateway-population-density-data/)
- [Quality-On-Demand](https://apis.io/collections/gsma/open-gsma-open-gateway-quality-on-demand/)
- [SIM Swap](https://apis.io/collections/gsma/open-gsma-open-gateway-sim-swap/)
- [Simple Edge Discovery](https://apis.io/collections/gsma/open-gsma-open-gateway-simple-edge-discovery/)

#### Overlays (18)

OpenAPI overlays, including conversational phrasing for each operation.

- [Gsma Mobile Money Api Overlay](https://apis.io/overlays/gsma/gsma-mobile-money-api-overlay/)
- [Gsma Open Gateway Call Forwarding Signal Overlay](https://apis.io/overlays/gsma/gsma-open-gateway-call-forwarding-signal-overlay/)
- [Gsma Open Gateway Carrier Billing Overlay](https://apis.io/overlays/gsma/gsma-open-gateway-carrier-billing-overlay/)
- [Gsma Open Gateway Carrier Billing Refund Overlay](https://apis.io/overlays/gsma/gsma-open-gateway-carrier-billing-refund-overlay/)
- [Gsma Open Gateway Device Identifier Overlay](https://apis.io/overlays/gsma/gsma-open-gateway-device-identifier-overlay/)
- [Gsma Open Gateway Device Location Retrieval Overlay](https://apis.io/overlays/gsma/gsma-open-gateway-device-location-retrieval-overlay/)
- [Gsma Open Gateway Device Location Verification Overlay](https://apis.io/overlays/gsma/gsma-open-gateway-device-location-verification-overlay/)
- [Gsma Open Gateway Device Reachability Status Overlay](https://apis.io/overlays/gsma/gsma-open-gateway-device-reachability-status-overlay/)
- [Gsma Open Gateway Device Roaming Status Overlay](https://apis.io/overlays/gsma/gsma-open-gateway-device-roaming-status-overlay/)
- [Gsma Open Gateway Device Swap Overlay](https://apis.io/overlays/gsma/gsma-open-gateway-device-swap-overlay/)
- [Gsma Open Gateway Home Devices Quality On Demand Overlay](https://apis.io/overlays/gsma/gsma-open-gateway-home-devices-quality-on-demand-overlay/)
- [Gsma Open Gateway Know Your Customer Overlay](https://apis.io/overlays/gsma/gsma-open-gateway-know-your-customer-overlay/)
- [Gsma Open Gateway Number Verification Overlay](https://apis.io/overlays/gsma/gsma-open-gateway-number-verification-overlay/)
- [Gsma Open Gateway Otp Validation Overlay](https://apis.io/overlays/gsma/gsma-open-gateway-otp-validation-overlay/)
- [Gsma Open Gateway Population Density Data Overlay](https://apis.io/overlays/gsma/gsma-open-gateway-population-density-data-overlay/)
- [Gsma Open Gateway Quality On Demand Overlay](https://apis.io/overlays/gsma/gsma-open-gateway-quality-on-demand-overlay/)
- [Gsma Open Gateway Sim Swap Overlay](https://apis.io/overlays/gsma/gsma-open-gateway-sim-swap-overlay/)
- [Gsma Open Gateway Simple Edge Discovery Overlay](https://apis.io/overlays/gsma/gsma-open-gateway-simple-edge-discovery-overlay/)

#### Security (3)

Authentication, trust centre, and vulnerability disclosure.

- [Gsma Authentication](https://apis.io/security/gsma/gsma-authentication/)
- [Gsma Domain Security](https://apis.io/security/gsma/gsma-domain-security/)
- [Gsma Vulnerability Disclosure](https://apis.io/security/gsma/gsma-vulnerability-disclosure/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Gsma Scopes](https://apis.io/scopes/gsma/gsma-scopes/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.gsma.com/)
- [Documentation](https://open-gateway.gsma.com/docs)
- [Getting started](https://developer.mobilemoneyapi.io/sdks/getting-started/introduction.html)
- [API reference](https://developer.mobilemoneyapi.io/api-versions-1.2/resources/api-service-definition.html)
- [Sign up](https://developer.mobilemoneyapi.io/signup/)
- [Support](https://developer.mobilemoneyapi.io/support/)
- [Changelog](https://developer.mobilemoneyapi.io/api-versions-1.2/resources/change-list.html)
- [Blog](https://www.gsma.com/newsroom/)
- [Security](https://www.gsma.com/security/)
- [Terms of service](https://www.gsma.com/aboutus/legal)
- [Privacy policy](https://www.gsma.com/aboutus/legal/privacy)
- [GitHub](https://github.com/GSMA)

## API Evangelist rating

**Kin Score 54.3** — strong · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 73.2 |
| Contract quality | 56.2 |
| Contract governance | 4.5 |
| Operational transparency | 44.7 |
| Developer ergonomics | 78.0 |
| Access clarity | 23.7 |

**Agent readiness 40.2** — agent-native

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | documented (partial credit) |
| MCP Server | — |
| Auth Clarity | negotiable (partial credit) |
| Idempotency | documented (partial credit) |
| Error Semantics | verified |
| OpenAPI Examples | partial |
| Rate Limit Signal | — |
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
| Pagination Ratio | partial |
| Operation Distinctiveness | — |

**Regulatory alignment 48.3** — Telecommunications

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/gsma/](https://apis.io/providers/gsma/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for GSMA: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/gsma/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
