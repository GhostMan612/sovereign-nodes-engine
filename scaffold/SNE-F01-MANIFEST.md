# SNE-F01 v1.0.0 — Exact-path overwrite manifest

- **Required clean HEAD:** `148dc28cdbdf4970c8011d76762b31b8dcafea0b`.
- Archive root: `sovereign-nodes-engine/`. Unzip to `C:\` to merge with the local planning repo.
- **42 exact files: 37 ADD, 5 REPLACE.** No engine source, executables, commercial IWADs, scripts or `.git` members.
- The five REPLACE preimages are **Git blob SHA-1** values read at the exact parent commit. They are not ZIP SHA-256 checksums.
- File SHA-256 of every archive member except the checksum ledger itself is in `scaffold/SNE-F01-SHA256.json`.

## REPLACE — require identical original tracked blob, stop on mismatch

| Relative path | Exact parent Git blob SHA-1 |
|---|---|
| `blueprints/phases/PHASE-00-FOUNDATION.md` | `d2cfa6828f8a7be92b700042e38f942610647f4a` |
| `blueprints/research/RESEARCH-QUEUE.md` | `14e4187a3320f4d77a70c796584b4be3d8ae0ea2` |
| `governance/PHASE-00-REVIEW-GATES.md` | `84c299f6db19197bbc5c1f7a38eb39b8121a1d58` |
| `governance/WO-000F-AUTHORIZATION-MATRIX.md` | `1510ee3f41340215011da612f992cfde74d0e527` |
| `registry/PHASE-00-ARTIFACT-INDEX.md` | `aa5559e84aa6d04f9c24ee45ab54e1548f1dfa99` |

## ADD — must be absent before extraction

- `SNE-F01-INSTALL.md`
- `artifact-chain/acceptance/SNE-ACC-F01.md`
- `artifact-chain/evidence/SNE-EVD-F01.md`
- `artifact-chain/reconciliation/SNE-REC-F01.md`
- `artifact-chain/verification/SNE-VER-F01.md`
- `artifact-chain/work-orders/SNE-WO-F01.md`
- `blueprints/architecture/SNE-F01-SCOPE-BOUNDARIES.md`
- `blueprints/diagrams/SNE-F01-AUTHORIZATION-LIFECYCLE.md`
- `blueprints/verification/SNE-F01-AGENT-DISPATCH-CONTRACT.md`
- `blueprints/verification/SNE-F01-AUTHORIZATION-LIFECYCLE.md`
- `blueprints/verification/SNE-F01-BUILD-RUN-LANES.md`
- `blueprints/verification/SNE-F01-DEPENDENCY-NETWORK-CONTROLS.md`
- `blueprints/verification/SNE-F01-EVIDENCE-CHAIN-AND-RETENTION.md`
- `blueprints/verification/SNE-F01-F02-ENTRY-GATE.md`
- `blueprints/verification/SNE-F01-FIXTURE-LANE.md`
- `blueprints/verification/SNE-F01-HOST-INVENTORY-LANE.md`
- `blueprints/verification/SNE-F01-PATH-DATA-BOUNDARIES.md`
- `blueprints/verification/SNE-F01-PERFORMANCE-ADMISSION.md`
- `blueprints/verification/SNE-F01-READ-ONLY-REVIEW-LANE.md`
- `blueprints/verification/SNE-F01-SCOPE-FREEZE.md`
- `blueprints/verification/SNE-F01-STOP-REVOKE-ROLLBACK.md`
- `docs/SNE-F01-START-HERE.md`
- `governance/SNE-F01-AUTHOR-REVIEW.md`
- `governance/SNE-F01-DECISION-LOG.md`
- `governance/SNE-F01-INDEPENDENCE-APPOINTMENT.md`
- `governance/SNE-F01-RISK-REGISTER.md`
- `scaffold/SNE-F01-BUILD-VERIFICATION.json`
- `scaffold/SNE-F01-CHANGELOG.md`
- `scaffold/SNE-F01-MANIFEST.md`
- `scaffold/SNE-F01-SHA256.json`
- `templates/SNE-F01-AUTHORIZATION.json`
- `templates/SNE-F01-AUTHORIZATION.schema.json`
- `templates/SNE-F01-CHANGE-REQUEST.json`
- `templates/SNE-F01-README.md`
- `templates/SNE-F01-REVIEW-ATTESTATION.json`
- `templates/SNE-F01-REVOCATION.json`
- `templates/SNE-F01-SCOPE-FREEZE.json`

## Validation contract

Confirm the local repo is clean before extracting. The archived preimage manifest cannot protect uncommitted customized work if blindly overwritten by an unzipper. No force-overwrite on a wrong branch, unexpected existing ADD path, or mismatched SHA. Stage only the explicit paths, verify staged diff includes 42 files and no deletions, then the operator alone commits/pushes. Document publication never grants test/build authorization.
