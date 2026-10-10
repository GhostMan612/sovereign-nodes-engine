# F-03 v1.2.0 — Exact overwrite manifest

- Expected **clean** pre-extraction `main` HEAD: `f2f2cfec676b9a5254fa2a5a7e6f08198581fa09`.
- Archive root: `sovereign-nodes-engine/` (extract ZIP to `C:\`, not into repo directory).
- Actions: **49 total, 43 ADD, 6 REPLACE**, zero DELETE, Markdown/JSON only.
- Every ADD must be absent; do not overwrite new/untracked local files. Every REPLACE Git tracked blob preimage SHA-1 must match below. A clean HEAD is also mandatory; preimage SHA alone cannot protect dirty files.
- File byte SHA-256 details: `scaffold/SNE-F03-SHA256.json`; manifest checksums are for *package members*, not tests/binaries.

## REPLACE preimage Git blob SHA-1 (at f2f2cfec676b9a5254fa2a5a7e6f08198581fa09)

| Path | Required blob SHA-1 |
|---|---|
| `blueprints/phases/PHASE-00-FOUNDATION.md` | `4f8899a463eec290768e5a692d01a285a470f910` |
| `blueprints/research/RESEARCH-QUEUE.md` | `37bc314167689ced6b8f6332cd27730dc49ec99a` |
| `blueprints/verification/SNE-000F-RESULT-REGISTER.md` | `abbea78d60f9c4fc14cbfc89a22fa67e47989745` |
| `evidence/sources/SOURCE-INDEX.md` | `95396501fdb315b2d9a31575436816c317bfd944` |
| `governance/PHASE-00-REVIEW-GATES.md` | `71f2d9c23b8fa8408f9bfe7744457f111138aab5` |
| `registry/PHASE-00-ARTIFACT-INDEX.md` | `79af429900c95754614bf2c5ea4316be8ceed6c2` |

## ADD (must NOT exist before extraction)

- `SNE-F03-INSTALL.md`
- `artifact-chain/acceptance/SNE-ACC-F03.md`
- `artifact-chain/evidence/SNE-EVD-F03.md`
- `artifact-chain/reconciliation/SNE-REC-F03.md`
- `artifact-chain/verification/SNE-VER-F03.md`
- `artifact-chain/work-orders/SNE-WO-F03.md`
- `blueprints/architecture/SNE-F03-BUILD-BOUNDARY.md`
- `blueprints/diagrams/SNE-F03-BUILD-GATE-GRAPH.md`
- `blueprints/verification/SNE-F03-ADMISSION.md`
- `blueprints/verification/SNE-F03-BIASEDDOOM-EXPERIMENT.md`
- `blueprints/verification/SNE-F03-BUILD-FAILURE-TAXONOMY.md`
- `blueprints/verification/SNE-F03-CMAKE-CONFIGURATION.md`
- `blueprints/verification/SNE-F03-COMMAND-PLAN.md`
- `blueprints/verification/SNE-F03-DEPENDENCY-DRIFT.md`
- `blueprints/verification/SNE-F03-DEPENDENCY-SBOM.md`
- `blueprints/verification/SNE-F03-F04-ENTRY.md`
- `blueprints/verification/SNE-F03-GENERATOR-MATRIX.md`
- `blueprints/verification/SNE-F03-GZDOOM-CONTROL.md`
- `blueprints/verification/SNE-F03-OPERATOR-HANDOFF.md`
- `blueprints/verification/SNE-F03-RED-FLAGS.md`
- `blueprints/verification/SNE-F03-REPRODUCIBILITY-TRIALS.md`
- `blueprints/verification/SNE-F03-RESOURCE-HASHES.md`
- `blueprints/verification/SNE-F03-SECURITY-AND-LEGAL.md`
- `blueprints/verification/SNE-F03-SOURCE-IMMUTABILITY.md`
- `blueprints/verification/SNE-F03-STOP-ROLLBACK.md`
- `blueprints/verification/SNE-F03-UZDOOM-COMPARATOR.md`
- `blueprints/verification/SNE-F03-WINDOWS-TOOLCHAIN.md`
- `docs/SNE-F03-START-HERE.md`
- `evidence/sources/SNE-F03-CMAKE-OBSERVATIONS.md`
- `evidence/sources/SNE-F03-SOURCE-PINS.md`
- `governance/SNE-F03-AUTHOR-REVIEW.md`
- `governance/SNE-F03-AUTHORIZATION-REQUEST.md`
- `governance/SNE-F03-RISK-REGISTER.md`
- `scaffold/SNE-F03-BUILD-VERIFICATION.json`
- `scaffold/SNE-F03-CHANGELOG.md`
- `scaffold/SNE-F03-MANIFEST.md`
- `scaffold/SNE-F03-SHA256.json`
- `templates/SNE-F03-BUILD-RECORD.json`
- `templates/SNE-F03-DEPENDENCY-ROW.json`
- `templates/SNE-F03-HOST-READINESS.json`
- `templates/SNE-F03-README.md`
- `templates/SNE-F03-REPRO-RECORD.json`
- `templates/SNE-F03-RESOURCE-RECORD.json`

## Scope and rollback

The ZIP contains no executable scripts, runtime files or engine/game source. Operator inspects current tree and staged diff, stages explicit manifest paths only. If wrong HEAD, dirty work, new file collision, source/version discrepancy or failed SHA verification: **STOP and manually reconcile**. Do not `git reset --hard`, `git clean`, force-push, `git add .` or delete unrelated files. This manifest never grants AUTH-H or AUTH-B.
