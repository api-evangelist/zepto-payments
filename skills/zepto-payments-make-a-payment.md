---
name: Make an account-to-account payment with Zepto
description: Authenticate, look up or create a payee contact, then send a real-time A2A payout over NPP/BECS and track it to completion.
api: openapi/zepto-payments-zepto.yml
operations: [GetUserDetails, ListAllContacts, AddAnAnyoneContact, MakeAPayment, GetAPayment, VoidAPayment]
---

# Make a payment (payout) with Zepto

Move money to a bank account over the New Payments Platform (NPP) or BECS Direct Entry.

## Auth
- OAuth2 authorization-code flow (`/oauth/authorize` → `/oauth/token`). Request the `payments` scope (plus `contacts` if creating a payee). Send the access token as `Authorization: Bearer <token>`.
- Use the sandbox host `https://api.sandbox.zeptopayments.com` first; production is `https://api.zeptopayments.com`.

## Steps
1. `GetUserDetails` (`GET /user`) — confirm the authenticated account and its source bank/float account.
2. `ListAllContacts` (`GET /contacts`) — find an existing payee, or `AddAnAnyoneContact` (`POST /contacts/anyone`) to create one.
3. `MakeAPayment` (`POST /payments`) — send the payout. **Set the `Idempotency-Key` header** to a unique value so retries never double-pay (see conventions/zepto-payments-conventions.yml).
4. `GetAPayment` (`GET /payments/{payment_ref}`) — poll status, or subscribe to `payment.*` webhooks for async completion.
5. `VoidAPayment` (`DELETE /payouts/{ref}`) — cancel while still voidable.

## Failure handling
- Transaction-level failures return a reason code (E1xx/E2xx/E3xx) — see errors/zepto-payments-decline-codes.yml. Only `E253`, `E153`, `E301`, `E305`, `E307` are retryable.
- In sandbox, use magic amounts (e.g. `$2.52` → E252 Insufficient Funds) to exercise failures — see sandbox/zepto-payments-sandbox.yml.
