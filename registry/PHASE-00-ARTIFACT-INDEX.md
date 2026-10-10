# Phase 00 — Work-order registry v0.9.0 (F-00 reviewer handoff)

| Work order | Main artifact | Last user-pushed Git checkpoint | Current documentary and technical state |
|---|---|---|---|
| WO-A | `SNE-WO-000A.md` | `369722f` | PUBLISHED; formal acceptance PENDING |
| WO-B | `SNE-WO-000B.md` | `edc274f` | PUBLISHED; formal acceptance PENDING |
| WO-C | `SNE-WO-000C.md` | `706db57` | PUBLISHED; C-series NOT RUN |
| WO-D | `SNE-WO-000D.md` | `1f21e4c` | PUBLISHED; native build/UHD NOT RUN |
| WO-E | `SNE-WO-000E.md` | `1644fb8` | PUBLISHED; ADR HOLD and G7 OPEN |
| WO-F | `SNE-WO-000F.md` | `1c01d2ff5bc3a1369210a7d68dd58269ecf6506d` | PUBLISHED; verification readiness, no execution authority |
| **F-00** | `artifact-chain/work-orders/SNE-WO-F00.md` | **v0.9.0 overlay prepared; Git commit not yet known** | AUTHOR SOURCE RECHECK; independent review PENDING |

## New F-00 sub-workorder artifacts

| Category | Canonical paths | State |
|---|---|---|
| Start and authority | `docs/SNE-F00-START-HERE.md`; `artifact-chain/work-orders/SNE-WO-F00.md` | DOCUMENTATION PREPARED |
| Audit source claims | `blueprints/verification/SNE-F00-CLAIM-CATALOG.md` | 16 selected source claims; no reviewer |
| Discriminating critiques | `SNE-F00-SPRITE-PARSER-REVIEW.md`; `SNE-F00-HANDOFF-PARSER-REVIEW.md`; `SNE-F00-PK3-VALIDATOR-REVIEW.md` in `blueprints/verification/` | AUTHOR HYPOTHESES, NOT RUN |
| Source ledgers | `evidence/sources/SNE-F00-PIN-LEDGER.md`; `SNE-F00-GAME-PRIMARY-OBSERVATIONS.md` / `SNE-F00-ENGINE-PRIMARY-OBSERVATIONS.md` | PINNED AUTHOR SOURCE |
| Reviewer governance | `governance/SNE-F00-REVIEW-ASSIGNMENT.md`; `SNE-F00-AUTHOR-FINDINGS.md`; `SNE-F00-RISK-REGISTER.md` | INDEPENDENT PENDING |
| Review form templates | `templates/SNE-F00-*.json` | BLANK, NO PASS |
| Evidence and acceptance | `artifact-chain/evidence/SNE-EVD-F00.md`; `artifact-chain/acceptance/SNE-ACC-F00.md` | SOURCE PACKET, NOT ACCEPTED |
| Archive reproducibility | `scaffold/SNE-F00-MANIFEST.md`; `scaffold/SNE-F00-SHA256.json`; `SNE-F00-INSTALL.md` | PACKAGE VALIDATION ONLY |
| Foundation ADR | `blueprints/decisions/ADR-SNE-002-FOUNDATION-PENDING.md` | **HOLD / UNMODIFIED** |

**Next:** external independent source review and operator reconciliation, then explicitly scoped **F-01 authorization** and, when separately approved, F-02 synthetic/original parity. No engine source changes are allowed by F-00.
