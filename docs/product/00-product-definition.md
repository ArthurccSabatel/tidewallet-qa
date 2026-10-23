# TideWallet: Product Definition

**Status:** Draft v0.1
**Type:** Fictional product (portfolio project)
**Market:** Brazil, currency BRL

## 1. Vision

TideWallet is a simple digital wallet that lets everyday users hold money, move it between accounts, see exactly where it went, and grow it with a basic savings feature.

**Positioning statement:** For people who want a clear and trustworthy place to manage small amounts of money, TideWallet is a digital wallet that makes every balance and every transaction easy to understand.

## 2. Problem

Users of digital wallets commonly face three pain points:

- They do not trust the balance when transfers are delayed, duplicated or fail silently.
- Statements are hard to read, so they cannot tell fees from transfers.
- Savings products are opaque: users cannot predict what they will earn.

## 3. Target users (initial personas)

| Persona | Description | Main need |
|---------|-------------|-----------|
| Marina, 28 | Freelance designer who receives and sends many small payments | Fast transfers and a clear statement |
| Carlos, 45 | Small shop owner who moves money between personal and business accounts | Reliable limits and no duplicated transfers |
| Beatriz, 22 | University student starting to save | A simple, predictable savings feature |

Personas are fictional and will be expanded in the PRD.

## 4. Scope of version 1

### In scope

1. **Account and balance:** one wallet per user in BRL, with available balance.
2. **Deposit:** add money to the wallet (simulated funding source).
3. **Transfer:** send money to another TideWallet user by identifier.
4. **Statement:** chronological list of transactions with type, amount, fee and resulting balance.
5. **Savings simulation:** a calculator that projects earnings for a chosen amount and period.
6. **Limits and fees:** daily transfer limit, reduced nighttime limit and a fee on selected operations.

### Out of scope for version 1

- Real payment rails, cards and bank integrations
- Credit, loans and investments beyond the simulator
- Multi-currency support
- Mobile applications

## 5. Core business rules (initial, to be refined)

| ID | Rule |
|----|------|
| BR-01 | All amounts are in BRL, with two decimal places. |
| BR-02 | A transfer cannot exceed the available balance plus any applicable fee. |
| BR-03 | A transfer amount must be greater than zero and not exceed the daily limit. |
| BR-04 | The daily transfer limit is R$ 5.000,00. Between 20:00 and 06:00 the limit is R$ 1.000,00. |
| BR-05 | A transfer to the same account as the origin is not allowed. |
| BR-06 | Repeating the same request with the same idempotency key must not create a second transfer. |
| BR-07 | Fees are rounded half up to the nearest cent. |
| BR-08 | Every transaction must be reflected in the statement and in the balance, and the two must always reconcile. |

These rules deliberately include edge cases (limits, rounding, idempotency, time windows) because they are the areas where financial software usually breaks.

## 6. Success metrics (draft)

| Metric | Why it matters | Initial target |
|--------|----------------|----------------|
| Transfer success rate | Core promise of the product | 99.5% or higher |
| Reconciliation mismatches | Trust in the balance | 0 |
| Duplicated transfers | Money safety | 0 |
| Median transfer time | User experience | Under 2 seconds |
| Support tickets about balance | Signal of lost trust | Downward trend |

## 7. Quality risks (preview)

The highest-risk areas, which will drive the test strategy:

1. Balance and statement inconsistency
2. Duplicated or lost transfers under retries and concurrency
3. Wrong fee or limit calculation, especially around rounding and the nighttime window
4. Incorrect savings projections
5. Unauthorized access to another user's wallet

## 8. Next steps

- Expand this definition into a full PRD (day 4 onward)
- Write user stories with Gherkin acceptance criteria
- Turn the business rules into a traceable requirements table
