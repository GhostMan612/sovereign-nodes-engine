# SNE-WO-000D v0.6.0 — Exact-file overwrite overlay manifest

- Exact clean local Git base: `706db57a4fbabd701244dd9e4674a59f7ab044f3`
- ZIP root: `sovereign-nodes-engine/`; intended extraction into `C:\` merges into `C:\sovereign-nodes-engine`.
- Markdown and JSON documentation only; no `.git` paths, executables, game code, WAD/IWADs or installer scripts.
- Each REPLACE path has immutable expected original Git blob SHA-1, captured by connected GitHub review of the pinned commit. Extraction itself **cannot** validate those preimages.
- SHA-256 ledger checks every other member; self-referential ledger intentionally excluded.
- Staging MUST use explicit exact paths, never `git add .` or `git add -A`.

## Exact contents

| Operation | Repo-relative path | Expected existing Git blob SHA-1 |
|---|---|---|
| ADD | `WO-000D-INSTALL.md` | — |
| ADD | `artifact-chain/acceptance/SNE-ACC-000D.md` | — |
| ADD | `artifact-chain/evidence/SNE-EVD-000D.md` | — |
| ADD | `artifact-chain/reconciliation/SNE-REC-000D.md` | — |
| ADD | `artifact-chain/verification/SNE-VER-000D.md` | — |
| REPLACE | `artifact-chain/work-orders/SNE-WO-000D.md` | `05e503642f58372edb49c53abf13aebec15497a9` |
| ADD | `blueprints/architecture/SNE-000D-EXECUTION-BOUNDARY.md` | — |
| ADD | `blueprints/diagrams/SNE-000D-REPRODUCIBILITY-FLOW.md` | — |
| REPLACE | `blueprints/research/DEPENDENCY-LICENSE-MATRIX.md` | `7fb7ced7137abef48b7ff4e155928db830e316a2` |
| REPLACE | `blueprints/research/HARDWARE-BENCHMARK-PLAN.md` | `5eaccfd6b76672e0a84753d0029a215f002d9527` |
| REPLACE | `blueprints/research/RESEARCH-QUEUE.md` | `591ade874fe37b3a53967d182e6cfe29a7398f49` |
| REPLACE | `blueprints/research/SNE-000B-COMPILER-BUILD-MATRIX.md` | `cf52770e61f8b6ee243d32b605521ddbb4f0e0c6` |
| ADD | `blueprints/research/SNE-000D-ARTIFACT-PROVENANCE.md` | — |
| ADD | `blueprints/research/SNE-000D-BUILD-FAILURE-TAXONOMY.md` | — |
| ADD | `blueprints/research/SNE-000D-BUILD-LANE-MATRIX.md` | — |
| ADD | `blueprints/research/SNE-000D-CMAKE-OPTIONS.md` | — |
| ADD | `blueprints/research/SNE-000D-COMPILER-TOOLCHAIN.md` | — |
| ADD | `blueprints/research/SNE-000D-DEPENDENCY-LOCK-PROTOCOL.md` | — |
| ADD | `blueprints/research/SNE-000D-HARDWARE-CAPTURE.md` | — |
| ADD | `blueprints/research/SNE-000D-MEASUREMENT-SOP.md` | — |
| ADD | `blueprints/research/SNE-000D-OPEN-QUESTIONS.md` | — |
| ADD | `blueprints/research/SNE-000D-PERFORMANCE-DECISION-GATES.md` | — |
| ADD | `blueprints/research/SNE-000D-REPRO-BUILD-COMMANDS.md` | — |
| ADD | `blueprints/research/SNE-000D-TEST-SCENES.md` | — |
| ADD | `blueprints/research/SNE-000D-THREAT-LICENSE-CHECKLIST.md` | — |
| ADD | `blueprints/research/SNE-000D-WINDOWS-ENV-INVENTORY.md` | — |
| ADD | `docs/WO-000D-START-HERE.md` | — |
| ADD | `evidence/sources/SNE-000D-PIN-LEDGER.md` | — |
| ADD | `evidence/sources/SNE-SRC-BIASEDDOOM-004.md` | — |
| ADD | `evidence/sources/SNE-SRC-GZDOOM-004.md` | — |
| ADD | `evidence/sources/SNE-SRC-UZDOOM-004.md` | — |
| REPLACE | `evidence/sources/SOURCE-INDEX.md` | `81dc31193a275d21c86081d8ca50a683e3d74160` |
| ADD | `governance/WO-000D-REVIEW-FINDINGS.md` | — |
| ADD | `governance/WO-000D-RISK-REGISTER.md` | — |
| REPLACE | `registry/PHASE-00-ARTIFACT-INDEX.md` | `df40ab6935a428073b2799129e8ae0d200e610fc` |
| ADD | `scaffold/WO-000D-BUILD-VERIFICATION.json` | — |
| ADD | `scaffold/WO-000D-CHANGELOG.md` | — |
| ADD | `scaffold/WO-000D-FILE-SHA256.json` | — |
| ADD | `scaffold/WO-000D-MANIFEST.md` | — |
| ADD | `templates/SNE-000D-BUILD-RECORD.json` | — |
| ADD | `templates/SNE-000D-DEPENDENCY-RECORD.json` | — |
| ADD | `templates/SNE-000D-HARDWARE-RECORD.json` | — |
| ADD | `templates/SNE-000D-README.md` | — |
| ADD | `templates/SNE-000D-REVIEW-RECORD.json` | — |
| ADD | `templates/SNE-000D-RUN-RECORD.json` | — |

## Counts

- REPLACE: 7
- ADD: 38
- TOTAL: 45

## Stop conditions

If local HEAD differs, working tree has unrelated modifications, any ADD already exists, or any REPLACE blob differs from expected: **STOP**, preserve files and reconcile manually. Overwriting arbitrary local changes is outside authorization. No Phase 00 runtime gate becomes green by installing the research packet.
