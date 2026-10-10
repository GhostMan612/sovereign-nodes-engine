# WO-E — Independent reviewer checklist handoff sheet

> This is a list of review obligations, **not a review performed**.

## Minimum review package

- `docs/WO-000E-START-HERE.md` and `SNE-000E-FOUNDATION-PIN-LEDGER.md`.
- ADR-SNE-002 and the candidate matrix, not just its conclusion.
- WO-C parity test-case catalog and open questions.
- WO-D Windows build matrix, performance SOP and rights list.
- WO-E claim audit, red-team findings, evidence gaps, security boundaries and fallback plan.

## Review stop rules

- Sample representative non-critical claims, and review **all critical claim IDs** in `SNE-000E-CLAIM-AUDIT.md`.
- Reject PASS statements unsupported by actual source/fixture/driver/log evidence.
- Demand raw build/benchmark evidence if a future iteration claims hardware readiness.
- Record negative findings and unresolved debate without editing historical evidence deceptively.
- Sign as independent only if truly independent of authored packet.

## Output expectation

A review record with exact input Git SHA, reviewer qualifications, reviewed URLs, corrected findings, unreviewed limits, explicit objection list, conditional recommendation and signature/date. If such a reviewer has not been engaged, continue to report **G7 PENDING**.
