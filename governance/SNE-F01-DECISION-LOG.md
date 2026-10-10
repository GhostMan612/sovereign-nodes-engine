# F-01 — Operator decision log (not yet signed)

| Decision ID | Question | Current state | Consequence |
|---|---|---|---|
| F01-DEC-01 | Appoint independent F-00 source reviewer? | PENDING | G1/G7 remain open until real review |
| F01-DEC-02 | Permit immutable public source-only `AUTH-R`? | PROPOSED, NO APPROVAL | no appointment/execution |
| F01-DEC-03 | Permit exact host metadata `AUTH-H`? | PROPOSED, NO APPROVAL | no local Windows inspection |
| F01-DEC-04 | Permit synthetic B1/B2 fixture `AUTH-F`? | NOT REQUESTED | no local writes or tests |
| F01-DEC-05 | Permit builds/game/benchmark (`AUTH-B/T/P`)? | NOT REQUESTED | do not start any binary/runtime |
| F01-DEC-06 | Permit implementation/redistribution (`AUTH-I/D`)? | NOT REQUESTED | excluded from F-01 |
| F01-DEC-07 | Accept v1.0.0 as documentation only? | PENDING | acceptance is separate from Git publication |
| F01-DEC-08 | Select engine foundation (`ADR-SNE-002`)? | HOLD | no Phase 01 work |

## How a future decision is recorded

Use `templates/SNE-F01-AUTHORIZATION.json` for **one category** and a private signed decision bound to that exact scope and digest, then a curated operator outcome in a new dated ledger entry. A pending/draft decision must not be changed to APPROVED without genuine operator action. Preserve previous IDs and rejected scopes for audit; do not rewrite history or push private signatures.
