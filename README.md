# Zepto (zepto-payments)

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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Zepto is a Gold Coast, Australia based account-to-account (A2A) payments company that gives merchants and platforms programmable, real-time access to Australia's core money-movement rails: the New Payments Platform (NPP) for instant A2A payments, PayTo for mandated real-time debits, PayID addressing, BECS Direct Entry (direct debit/credit) and stored-value float accounts — with real-time messaging, settlement and reconciliation. Zepto is the first non-authorised-deposit-taking institution (non-ADI) approved to connect directly to the NPP as a "Connected Institution" for PayTo, making it an infrastructure-grade money-movement provider rather than a card acquirer.

Zepto's posture is genuinely developer-first: a public ReadMe developer portal, a full sandbox, idempotent asynchronous payment flows, webhook notifications, and seven downloadable OpenAPI specifications.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/zepto-payments/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/zepto-payments/refs/heads/main/apis.yml)

## Tags

- Payments
- Australia
- Real-Time Payments
- Account-to-Account
- New Payments Platform
- PayTo
- PayID
- Direct Entry
- Open Banking
- Money Movement

## Timestamps

- **Created:** 2026-07-24
- **Modified:** 2026-07-24

## Authentication

- **Core Zepto API:** OAuth2 authorization-code flow (authorizationUrl `/oauth/authorize`, tokenUrl `/oauth/token`) with scoped access tokens — `public`, `contacts`, `payments`, `payment_requests`, `refunds`, `agreements`, `transactions`, `open_agreements`, `transfers`.
- **Product APIs (PayTo, Validate, Investigations, Clients, Merchant Reports, Notifications):** HTTP Bearer token.
- **Idempotency:** `Idempotency-Key` header supported for asynchronous payment flows.
- **Base URLs:** production `https://api.zeptopayments.com` · sandbox `https://api.sandbox.zeptopayments.com`

## APIs

### Zepto API

Core account-to-account payments API — move money over NPP, BECS Direct Entry and PayID with payments, payouts, payment requests, transfers, refunds, agreements, contacts, bank accounts and transaction history.

- **Human URL:** [https://docs.zeptopayments.com/reference/zepto-api](https://docs.zeptopayments.com/reference/zepto-api)
- **Base URL:** `https://api.zeptopayments.com`
- [OpenAPI](openapi/zepto-payments-zepto.yml)

### Zepto PayTo API

Programmatic PayTo mandate management and real-time collection — create, amend, suspend, reactivate and cancel PayTo agreements, then collect authorised real-time payments and issue refunds.

- **Human URL:** [https://docs.zeptopayments.com/reference/agreements](https://docs.zeptopayments.com/reference/agreements)
- **Base URL:** `https://api.zeptopayments.com`
- [OpenAPI](openapi/zepto-payments-pay-to.yml)

### Zepto Validate API (Confirmation of Payee)

Confirmation of Payee (CoP) account validation — verify a payee's account name against account details in real time before initiating a payment.

- **Human URL:** [https://docs.zeptopayments.com/reference/cop-account-validations](https://docs.zeptopayments.com/reference/cop-account-validations)
- **Base URL:** `https://api.zeptopayments.com`
- [OpenAPI](openapi/zepto-payments-validate-cop.yml)

### Zepto Investigations API

Disputes and investigations (Beta) — raise and manage payment disputes, respond to action requests (accept, reject, upload evidence).

- **Human URL:** [https://docs.zeptopayments.com/reference/disputes-beta](https://docs.zeptopayments.com/reference/disputes-beta)
- **Base URL:** `https://api.zeptopayments.com`
- [OpenAPI](openapi/zepto-payments-investigations.yml)

### Zepto Clients API

Client management (Alpha) — create and manage sub-clients and their Merchant Category Codes (MCC) for platform and marketplace models.

- **Human URL:** [https://docs.zeptopayments.com/reference/clients](https://docs.zeptopayments.com/reference/clients)
- **Base URL:** `https://api.zeptopayments.com`
- [OpenAPI](openapi/zepto-payments-clients.yml)

### Zepto Merchant Reports API

Merchant reporting — download PayTo settlement reports by report date for reconciliation.

- **Human URL:** [https://docs.zeptopayments.com/reference/openapi-specifications](https://docs.zeptopayments.com/reference/openapi-specifications)
- **Base URL:** `https://api.zeptopayments.com`
- [OpenAPI](openapi/zepto-payments-merchant-reports.yml)

### Zepto Notifications API (Webhooks)

Webhook event notifications — subscribe to asynchronous payment and account events (e.g. `float_accounts.unmatched_credit.received`).

- **Human URL:** [https://docs.zeptopayments.com/docs/setting-up-your-webhooks](https://docs.zeptopayments.com/docs/setting-up-your-webhooks)
- **Base URL:** `https://api.zeptopayments.com`
- [OpenAPI](openapi/zepto-payments-notifications.yml)

## Common Properties

- [Website](https://zepto.com.au/)
- [Developer Portal](https://zepto.com.au/developers/)
- [Documentation](https://docs.zeptopayments.com/)
- [API Reference](https://docs.zeptopayments.com/reference/openapi-specifications)
- [Getting Started](https://docs.zeptopayments.com/docs/getting-started-in-sandbox)
- [Change Log](https://docs.zeptopayments.com/reference/change-log)
- [Status Page](https://status.zeptopayments.com/)
- [Help Center](https://help.zepto.money/en/)
- [Login](https://go.zeptopayments.com/sign_in)
- [Blog](https://zepto.com.au/blog)
- [LinkedIn](https://www.linkedin.com/company/zepto-payments)
- [Terms of Service](https://zepto.com.au/website-terms)
- [Privacy Policy](https://zepto.com.au/legal-and-privacy-policy)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
