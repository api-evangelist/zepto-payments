---
name: Set up a PayTo agreement and collect payment
description: Create a PayTo mandate, wait for the debtor to authorise it, then collect real-time payments and issue refunds against it.
api: openapi/zepto-payments-pay-to.yml
operations: [create agreement, show agreement, create payment, show payment, create refund]
---

# Collect with PayTo

Zepto is an NPP Connected Institution for PayTo — set up a mandate and collect authorised real-time debits.

## Auth
- HTTP Bearer token (`Authorization: Bearer <token>`) against `POST /payto/*` on the sandbox or production host.

## Steps
1. `POST /payto/alias_resolution` — resolve the debtor's PayID/BSB before creating the mandate.
2. `POST /payto/agreements` (create agreement) — create the PayTo mandate; capture the returned `agreement_uid`.
3. `GET /payto/agreements/{agreement_uid}` (show agreement) — poll until the debtor authorises. In sandbox, drive this with `POST /payto/agreements/{agreement_uid}/simulate_debtor_action`.
4. `POST /payto/payments` (create payment) — collect against the active agreement; poll with `GET /payto/payments/{payment_uid}` or retry with `POST /payto/payments/{payment_uid}/retry`.
5. `POST /payto/refunds` (create refund) — refund a collected payment; track via `GET /payto/refunds/{refund_uid}`.

## Notes
- Manage the mandate lifecycle with amendment / suspension / reactivation / cancellation endpoints.
- 422 responses carry PayTo unprocessable codes; failures carry reason codes — see errors/zepto-payments-decline-codes.yml and the PayTo reason-codes docs.
