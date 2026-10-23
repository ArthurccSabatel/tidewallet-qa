# TideWallet QA

A quality engineering portfolio project built around **TideWallet**, a fictional digital wallet. It shows how product thinking, business analysis and QA automation fit together in a financial domain.

> TideWallet is a fictional product created for learning and portfolio purposes. It does not process real money and is not affiliated with any financial institution.

## Why this project exists

Financial systems punish small mistakes: a rounding error, a duplicated transfer or a wrong balance has real cost. This repository documents how a QA professional can work across the whole lifecycle of such a product:

1. **Product**: problem framing, personas, scope and success metrics.
2. **Business analysis**: user stories, acceptance criteria and business rules.
3. **Quality strategy**: risk-based test planning, test cases and traceability.
4. **Automation**: API, end-to-end, data and performance tests running in CI.
5. **Finance knowledge**: calculators, reconciliation and notes on payments, KYC and fraud.

## Repository structure

```
tidewallet-qa/
├── docs/
│   ├── product/          Product definition, PRD, personas, metrics
│   ├── requirements/     User stories (Gherkin) and business rules
│   └── qa/               Test strategy, test plan, cases, bug reports
├── tests/
│   ├── api/              API tests (Postman/Newman and Python)
│   ├── e2e/              End-to-end tests (Cypress)
│   ├── sql/              Data integrity and reconciliation checks
│   └── performance/      Load tests (k6)
├── docker/               Containerized test environment
├── reports/              Test and quality reports
├── finance-notes/        Domain notes (payments, KYC, fraud, calculators)
├── PROGRESS.md           Daily progress log
└── README.md
```

## Roadmap

| Phase | Focus | Status |
|-------|-------|--------|
| 1 | Foundation and product definition | In progress |
| 2 | PRD, personas, user stories, business rules | Planned |
| 3 | Risk-based test strategy, cases, traceability | Planned |
| 4 | API, E2E and SQL automation with CI | Planned |
| 5 | Docker environment, quality metrics, load testing | Planned |
| 6 | Finance domain: calculators, reconciliation, fraud notes | Planned |
| 7 | Case study and portfolio write-up | Planned |

## Tech stack

Cypress, JavaScript, Postman/Newman with Chai assertions, Python with pytest, SQL, k6, Docker, GitHub Actions.

## Author

Arthur Sabatel, QA Analyst focused on test automation.
LinkedIn: https://www.linkedin.com/in/arthur-sabatel-7513b3324
