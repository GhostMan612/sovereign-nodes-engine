# SNE-WO-000B v0.4.0 — Explicit overlay manifest

- Destination: `C:\`, archive root: `sovereign-nodes-engine/`
- Required base commit: `369722fcd0839447cd5ecf5b78aa1ca7d8e2645c`
- Extract only into a **clean** repository and stop on local conflicts.
- Scope: Markdown and JSON research, no executable files, no source code, no deletes, no `.git` modifications.
- Each REPLACE path must be checked against preimage Git blob SHA-1 in `WO-000B-FILE-SHA256.json` and the operator's local diff before installation.
- The checksum ledger omits its own checksum to avoid self-reference; it includes all other archive members.

## File action summary

The following table is a generated path list, with no unlisted files authorized:
| Action | Path |
|---|---|
| ADD | `WO-000B-INSTALL.md` |
| ADD | `artifact-chain/acceptance/SNE-ACC-000B.md` |
| ADD | `artifact-chain/evidence/SNE-EVD-000B.md` |
| ADD | `artifact-chain/reconciliation/SNE-REC-000B.md` |
| ADD | `artifact-chain/verification/SNE-VER-000B.md` |
| REPLACE | `artifact-chain/work-orders/SNE-WO-000B.md` |
| ADD | `blueprints/diagrams/SNE-000B-ENGINE-SEAMS.md` |
| REPLACE | `blueprints/research/CANDIDATE-MATRIX.md` |
| REPLACE | `blueprints/research/DEPENDENCY-LICENSE-MATRIX.md` |
| REPLACE | `blueprints/research/RESEARCH-QUEUE.md` |
| ADD | `blueprints/research/SNE-000B-COMPILER-BUILD-MATRIX.md` |
| ADD | `blueprints/research/SNE-000B-ENGINE-CODE-MAP.md` |
| ADD | `blueprints/research/SNE-000B-EXTENSION-SEAMS.md` |
| ADD | `blueprints/research/SNE-000B-MAINTENANCE-RISK.md` |
| ADD | `blueprints/research/SNE-000B-TEST-GATES.md` |
| REPLACE | `blueprints/research/UPSTREAM-CODE-MAP.md` |
| ADD | `docs/WO-000B-START-HERE.md` |
| ADD | `evidence/sources/SNE-SOURCE-PINS-000B.md` |
| ADD | `evidence/sources/SNE-SRC-BIASEDDOOM-002.md` |
| ADD | `evidence/sources/SNE-SRC-GZDOOM-002.md` |
| ADD | `evidence/sources/SNE-SRC-UZDOOM-002.md` |
| REPLACE | `evidence/sources/SOURCE-INDEX.md` |
| ADD | `governance/WO-000B-OPEN-RISKS.md` |
| ADD | `governance/WO-000B-REVIEW-FINDINGS.md` |
| REPLACE | `registry/PHASE-00-ARTIFACT-INDEX.md` |
| ADD | `scaffold/WO-000A-CHECKSUM-RECONCILIATION.md` |
| ADD | `scaffold/WO-000A-COMMITTED-SHA256.json` |
| ADD | `scaffold/WO-000B-BUILD-VERIFICATION.json` |
| ADD | `scaffold/WO-000B-CHANGELOG.md` |
| ADD | `scaffold/WO-000B-FILE-SHA256.json` |
| ADD | `scaffold/WO-000B-MANIFEST.md` |

## Preimage guardrails

For exact expected Git blob SHA-1s and archive SHA-256s, consult `scaffold/WO-000B-FILE-SHA256.json`. If a local REPLACE file has different content or your HEAD is not the expected commit, stop and review; extraction is not a three-way merge and will overwrite same-path files. Keep operator-reviewed backups.
