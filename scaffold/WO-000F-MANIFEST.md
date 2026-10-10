# SNE-WO-000F v0.8.0 — Exact overlay action manifest

- Parent Git commit: `1644fb80c3e2803dd19465292423832e8fdf8e24`; required clean baseline before extraction.
- Archive root: `sovereign-nodes-engine/`, extraction destination: `C:\`.
- Authorized files: **49 total; 43 ADD and 6 REPLACE**, Markdown and JSON only.
- `REPLACE` requires a matching **Git blob SHA-1 preimage**. The archive itself does not automatically verify the user's working tree.
- The SHA-256 ledger contains every other ZIP file, not itself, to avoid circular hashes.
- No paths deleted; no scripts, engine/game source files, binaries, `.git`, legal IWADs, real-person genealogy or sensitive logs.
- The ZIP validation report confirms archive/package checks only; no engine/device compatibility was executed.

| Action | Repo-relative file | Expected existing Git blob SHA-1 |
|---|---|---|
| ADD | `WO-000F-INSTALL.md` | — |
| ADD | `artifact-chain/acceptance/SNE-ACC-000F.md` | — |
| ADD | `artifact-chain/evidence/SNE-EVD-000F.md` | — |
| ADD | `artifact-chain/reconciliation/SNE-REC-000F.md` | — |
| ADD | `artifact-chain/verification/SNE-VER-000F.md` | — |
| ADD | `artifact-chain/work-orders/SNE-WO-000F.md` | — |
| ADD | `blueprints/architecture/SNE-000F-CLOSURE-ARCHITECTURE.md` | — |
| ADD | `blueprints/diagrams/SNE-000F-EVIDENCE-FLOW.md` | — |
| REPLACE | `blueprints/phases/PHASE-00-FOUNDATION.md` | `74ff7bcae725b76f0ec72c95090fe63810649fd8` |
| REPLACE | `blueprints/research/RESEARCH-QUEUE.md` | `1ec3f56214a96a0c236db445f028606e6360efb6` |
| REPLACE | `blueprints/research/SNE-000E-EVIDENCE-GAP-MATRIX.md` | `38652ac622199fc8ec811199e7a1fd6879e9aa23` |
| ADD | `blueprints/verification/AGENTS.md` | — |
| ADD | `blueprints/verification/SNE-000F-ADMISSION-CHECKLIST.md` | — |
| ADD | `blueprints/verification/SNE-000F-BASELINE-IDENTITY.md` | — |
| ADD | `blueprints/verification/SNE-000F-BUILD-ENTRY-GATE.md` | — |
| ADD | `blueprints/verification/SNE-000F-CASE-TO-GATE-TRACE.md` | — |
| ADD | `blueprints/verification/SNE-000F-FALSE-POSITIVE-CONTROLS.md` | — |
| ADD | `blueprints/verification/SNE-000F-FIXTURE-ISOLATION.md` | — |
| ADD | `blueprints/verification/SNE-000F-HANDOFF-TESTS.md` | — |
| ADD | `blueprints/verification/SNE-000F-HARDWARE-TRIAL-MATRIX.md` | — |
| ADD | `blueprints/verification/SNE-000F-MAINTENANCE-LEGAL.md` | — |
| ADD | `blueprints/verification/SNE-000F-PK3-AND-WAD-GATES.md` | — |
| ADD | `blueprints/verification/SNE-000F-RESULT-REGISTER.md` | — |
| ADD | `blueprints/verification/SNE-000F-RESULT-SEMANTICS.md` | — |
| ADD | `blueprints/verification/SNE-000F-REVIEW-ROLES.md` | — |
| ADD | `blueprints/verification/SNE-000F-SPRITE-TESTS.md` | — |
| ADD | `blueprints/verification/SNE-000F-STOP-ROLLBACK.md` | — |
| ADD | `blueprints/verification/SNE-000F-SUBWORKORDER-ORDER.md` | — |
| ADD | `blueprints/verification/SNE-000F-WINDOWS-INVENTORY.md` | — |
| ADD | `docs/WO-000F-START-HERE.md` | — |
| ADD | `evidence/sources/SNE-000F-SOURCE-SNAPSHOT.md` | — |
| ADD | `evidence/sources/SNE-SRC-GAME-005.md` | — |
| REPLACE | `evidence/sources/SOURCE-INDEX.md` | `38cf7e54191fec6cc2f90e8d03e0cb3b2cfefee5` |
| REPLACE | `governance/PHASE-00-REVIEW-GATES.md` | `44b7b7e4db668d47949fcddcb410c7d33c6681bd` |
| ADD | `governance/WO-000F-AUTHORIZATION-MATRIX.md` | — |
| ADD | `governance/WO-000F-INDEPENDENT-REVIEW-HANDOFF.md` | — |
| ADD | `governance/WO-000F-REVIEW-FINDINGS.md` | — |
| ADD | `governance/WO-000F-RISK-REGISTER.md` | — |
| REPLACE | `registry/PHASE-00-ARTIFACT-INDEX.md` | `026233993a221065e248062d8bde1478fd6d5b31` |
| ADD | `scaffold/WO-000F-BUILD-VERIFICATION.json` | — |
| ADD | `scaffold/WO-000F-CHANGELOG.md` | — |
| ADD | `scaffold/WO-000F-FILE-SHA256.json` | — |
| ADD | `scaffold/WO-000F-MANIFEST.md` | — |
| ADD | `templates/SNE-000F-AUTHORIZATION.json` | — |
| ADD | `templates/SNE-000F-CASE-RESULT.json` | — |
| ADD | `templates/SNE-000F-DEFECT-DISPOSITION.json` | — |
| ADD | `templates/SNE-000F-GATE-LEDGER.json` | — |
| ADD | `templates/SNE-000F-README.md` | — |
| ADD | `templates/SNE-000F-REVIEW-RESULT.json` | — |

## Conflict and rollback

If local HEAD differs or any ADD path already exists, STOP. Preserve operator edits and reconcile manually; do not force overwrite, force push, reset, or stage unrelated changes. Historical ledgers stay immutable.
The operator confirms the actual staged diff and remote push. This overlay does not close Phase 00 or authorize an engine implementation.
