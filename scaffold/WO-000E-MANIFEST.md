# SNE-WO-000E v0.7.0 — Exact-file overwrite archive manifest

- ZIP archive root: `sovereign-nodes-engine/` for extraction into **`C:\`**.
- Exact required **clean** local HEAD: `1f21e4c99da50c83ac0c90d14b2f14a752ae89f4`.
- Scope: documentation-only Markdown and JSON; no code, WAD/IWAD, executables, `.git`, deletes or private data.
- Actions: **8 REPLACE**, **40 ADD**, **48 total files**.
- Every replacement has an expected original Git blob SHA-1 captured from the pinned baseline. An extractor does **not** verify preimage: operator must do it before replacing files.
- `scaffold/WO-000E-FILE-SHA256.json` contains the SHA-256 of all package member raw bytes **except itself**. `WO-000E-BUILD-VERIFICATION.json` is archive QA, not engine QA.
- If HEAD differs, any ADD file already exists or working tree is dirty, **STOP**: do not overwrite; ask for reconciliation, no force reset.

## Exact actions / expected original blob SHA-1

| Action | Repo-relative path | SHA-1 preimage |
|---|---|---|
| ADD | `WO-000E-INSTALL.md` | — |
| ADD | `artifact-chain/acceptance/SNE-ACC-000E.md` | — |
| ADD | `artifact-chain/evidence/SNE-EVD-000E.md` | — |
| ADD | `artifact-chain/reconciliation/SNE-REC-000E.md` | — |
| ADD | `artifact-chain/verification/SNE-VER-000E.md` | — |
| REPLACE | `artifact-chain/work-orders/SNE-WO-000E.md` | `7ef2880dec9db83bdd2ff8b73b746e90a50c7947` |
| ADD | `blueprints/architecture/SNE-000E-BOUNDARY-REVIEW.md` | — |
| ADD | `blueprints/architecture/SNE-000E-DECISION-FLOW.md` | — |
| REPLACE | `blueprints/decisions/ADR-SNE-002-FOUNDATION-PENDING.md` | `4a0be9660d11b47d8a661f538bceb33547b81b38` |
| ADD | `blueprints/diagrams/SNE-000E-GATE-DEPENDENCIES.md` | — |
| REPLACE | `blueprints/phases/PHASE-00-FOUNDATION.md` | `3894c703565f37096f31511b8f548953f4c2934f` |
| REPLACE | `blueprints/research/CANDIDATE-MATRIX.md` | `517a0137a2a32de85216356d05c59838582f4db6` |
| REPLACE | `blueprints/research/RESEARCH-QUEUE.md` | `f60119e45cc31acf7133285be7717cab81c4db5d` |
| ADD | `blueprints/research/SNE-000E-ADAPTER-VS-FORK.md` | — |
| ADD | `blueprints/research/SNE-000E-ALTERNATIVES-ANALYSIS.md` | — |
| ADD | `blueprints/research/SNE-000E-CANDIDATE-TRADEOFFS.md` | — |
| ADD | `blueprints/research/SNE-000E-CLAIM-AUDIT.md` | — |
| ADD | `blueprints/research/SNE-000E-COST-AND-MAINTENANCE.md` | — |
| ADD | `blueprints/research/SNE-000E-EVIDENCE-GAP-MATRIX.md` | — |
| ADD | `blueprints/research/SNE-000E-EXPERIMENT-PRIORITY.md` | — |
| ADD | `blueprints/research/SNE-000E-FOUNDATION-SCORECARD.md` | — |
| ADD | `blueprints/research/SNE-000E-GAME-DEFECT-ISOLATION.md` | — |
| ADD | `blueprints/research/SNE-000E-LEGAL-POLICY-GATES.md` | — |
| ADD | `blueprints/research/SNE-000E-ROLLBACK-PLAN.md` | — |
| ADD | `blueprints/research/SNE-000E-SEAMLESSNESS-REALITY.md` | — |
| ADD | `blueprints/research/SNE-000E-SECURITY-BOUNDARIES.md` | — |
| ADD | `blueprints/research/SNE-000E-TOOLCHAIN-BLOCKERS.md` | — |
| ADD | `docs/WO-000E-START-HERE.md` | — |
| ADD | `evidence/sources/SNE-000E-FOUNDATION-PIN-LEDGER.md` | — |
| REPLACE | `evidence/sources/SOURCE-INDEX.md` | `bc739d8f0c2db3882cabe8fa5dc4ffebcb59347e` |
| REPLACE | `governance/PHASE-00-REVIEW-GATES.md` | `0ba5922834b70ed2dc1cf3fe183967a4c3c7abb9` |
| ADD | `governance/WO-000E-DECISION-CONDITIONS.md` | — |
| ADD | `governance/WO-000E-INDEPENDENT-REVIEW-PROTOCOL.md` | — |
| ADD | `governance/WO-000E-INDEPENDENT-REVIEW-READY.md` | — |
| ADD | `governance/WO-000E-RED-TEAM-FINDINGS.md` | — |
| ADD | `governance/WO-000E-REVIEWER-QUESTIONS.md` | — |
| ADD | `governance/WO-000E-RISK-REGISTER.md` | — |
| REPLACE | `registry/PHASE-00-ARTIFACT-INDEX.md` | `dfbf0f2bbe139eda578b51ef32bc17e68e62d9a6` |
| ADD | `scaffold/WO-000E-BUILD-VERIFICATION.json` | — |
| ADD | `scaffold/WO-000E-CHANGELOG.md` | — |
| ADD | `scaffold/WO-000E-FILE-SHA256.json` | — |
| ADD | `scaffold/WO-000E-MANIFEST.md` | — |
| ADD | `scaffold/WO-000E-SOURCE-CONFIDENCE.md` | — |
| ADD | `templates/SNE-000E-ADR-VOTE.json` | — |
| ADD | `templates/SNE-000E-COMPAT-PROOF.json` | — |
| ADD | `templates/SNE-000E-GATE-STATE.json` | — |
| ADD | `templates/SNE-000E-README.md` | — |
| ADD | `templates/SNE-000E-REVIEW-RECORD.json` | — |

## Untracked file and Git discipline

The package author verifies archive bytes; the operator checks staged additions and replacements using `git diff --cached --check` after **explicit-path** staging. The unstaged `git diff --check` does not inspect new files. Review `git diff --cached --name-only` equals the  complete inventory before commit. Keep full source history; GitHub remote push remains manual.

## Decision scope

SNE-WO-000E is a red-team **author** document, not a source-engine acceptance; ADR stays HOLD and independent reviewer remains PENDING. Publication does not make any benchmark or build PASS.
