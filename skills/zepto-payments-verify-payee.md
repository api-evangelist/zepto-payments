---
name: Verify a payee with Confirmation of Payee before paying
description: Run a Confirmation of Payee (CoP) account-name check to reduce misdirected payments and fraud before initiating a payment.
api: openapi/zepto-payments-validate-cop.yml
operations: [account name validation]
---

# Confirmation of Payee (Validate)

Check that a payee's account name matches the account details in real time before you pay.

## Auth
- HTTP Bearer token against `POST /cop/account/validate`.

## Steps
1. `POST /cop/account/validate` (account name validation) — submit the payee name + account details; receive a match / close-match / no-match result.
2. Gate the downstream `MakeAPayment` (core API) or PayTo collection on the CoP result.

## Notes
- Handle `429 Too Many Requests` with backoff — CoP is rate-limited (see errors/zepto-payments-problem-types.yml).
- `403` means the token lacks CoP permission; `422` means the request failed validation.
