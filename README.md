# Zepto (zepto-payments)

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
