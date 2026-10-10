# SNE-WO-F01 — Operator Authorization & Scope Freeze

- Phase: `SNE-P00`; release: `v1.0.0`; F sub-workstream: **F-01**.
- Required exact clean SNE repository parent: `148dc28cdbdf4970c8011d76762b31b8dcafea0b` (`main` as last pushed by operator).
- Existing game research pin: `44034e97fd22129f919a18cadceb84466ef1bcd3` (not a runtime build or approved local checkout).
- State: **AUTHORIZATION SYSTEM DOCUMENTED / ALL EXECUTION CATEGORIES UNAPPROVED**.
- Author may produce this Markdown/JSON overlay; operator alone decides and executes later local tasks and Git pushes.

## Mission

Specify a falsifiable, tightly scoped and revocable authorization interface between the finished Phase-00 plans and any future read-only inventory, disposable fixtures, native builds, game tests or hardware measurements. Distinguish permission to **plan** from permission to **act**. Maintain independent evidence review and human operator final signoff without silently escalating authority.

## Inputs

- Work orders A–F committed through `1c01d2f`; F-00 review *packet* committed as `148dc28cdbdf4970c8011d76762b31b8dcafea0b`; external independent G7 signoff remains unprovided.
- `governance/WO-000F-AUTHORIZATION-MATRIX.md` and `blueprints/verification/SNE-000F-SUBWORKORDER-ORDER.md` provide F-00→F-07 dependencies.
- `SNE-F00-CLAIM-CATALOG.md` describes 16 historical primary-source claims and unresolved validator/sprite/boolean concerns.
- `ADR-SNE-002` remains **HOLD**; C-001…C-015, native candidate builds, UHD 620 and legal/security clearance remain unexecuted.

## Deliverables

1. Explicit AUTH-R/H/F/B/T/P/S/I/D non-inheriting permission model, scope freeze, revocation/expiry, stop cases and agent handoff contract.
2. Precise proposed minimal `AUTH-R` external source-review intake, and separate `AUTH-H` **planning-only** Windows inventory lane.
3. Separate fixture/build/game/benchmark readiness plans with unambiguous local write boundaries and operator approval gates.
4. Operator request, freeze, amendment, revocation, and reviewer JSON records with all approvals **FALSE/null** and a validating draft-authorization JSON schema.
5. Complete file-exact overwrite manifest (Git preimage SHA-1), ZIP member SHA-256 ledger, packaging verification report, local PowerShell staging and rollback procedure.

## Invariants

- This package cannot approve itself; a text value `APPROVED` or a completed form in public Git is never independently sufficient proof of permission.
- No local machine process, game test, engine binary/build, dependency download, WAD redistribution, private Mantle access, remote Git operation or Phase 01 implementation is performed or authorized.
- A formal reviewer must be distinct from the A–F/F00 author and independently inspect source; appointment itself is missing at this point.
- No candidate is selected: proposed GZDoom-first **test sequence** does not close G8.

## Documentation exit gate

Archive and all schema examples parse; exact 5 replaces match `148dc28cdbdf4970c8011d76762b31b8dcafea0b` preimage; 37 additions have no pre-existing tracked path; every scope remains default denied; stopping and challenge paths explicit; staged Git diff reviewed by operator. No experiment or independent review is claimed complete.

## Future transition

The *operator*, after independently reviewing F-00 objections, may separately sign a **single category-specific** authorization. The recommended first request is `AUTH-R` for a qualified independent reviewer; any alternative `AUTH-H` read-only host inventory needs its own signed record. F-02/F-03 etc. require subsequent separate work orders and authorization.
