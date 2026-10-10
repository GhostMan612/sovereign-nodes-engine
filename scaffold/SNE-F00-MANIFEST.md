# SNE-F00 v0.9.0 — Explicit overlay manifest

- ZIP member root: `sovereign-nodes-engine/`.
- Intended merge: extract to `C:\` only.
- Required clean Git `main` HEAD: `1c01d2ff5bc3a1369210a7d68dd58269ecf6506d`.
- Exact intended actions: **6 REPLACE**, **39 ADD**, **45 total**.
- Every REPLACE expected blob is the GitHub-returned blob SHA-1 at the pinned baseline.
- Archive SHA-256 of member bytes excludes self-referential `scaffold/SNE-F00-SHA256.json`.
- Only Markdown and JSON; no scripts, engine/game source, .git, IWAD, asset binary, secrets or private data.
- Author selected source file recheck only; no independent G7 review or runtime test is claimed.

## Approved exact paths and actions

| Action | Repo-relative path | Expected blob SHA-1 at 1c01d2f |
|---|---|---|
| ADD | `SNE-F00-INSTALL.md` | — |
| ADD | `artifact-chain/acceptance/SNE-ACC-F00.md` | — |
| ADD | `artifact-chain/evidence/SNE-EVD-F00.md` | — |
| ADD | `artifact-chain/reconciliation/SNE-REC-F00.md` | — |
| ADD | `artifact-chain/verification/SNE-VER-F00.md` | — |
| ADD | `artifact-chain/work-orders/SNE-WO-F00.md` | — |
| ADD | `blueprints/architecture/SNE-F00-AUDIT-BOUNDARY.md` | — |
| ADD | `blueprints/diagrams/SNE-F00-REVIEW-FLOW.md` | — |
| REPLACE | `blueprints/phases/PHASE-00-FOUNDATION.md` | `d2cfa6828f8a7be92b700042e38f942610647f4a` |
| REPLACE | `blueprints/research/RESEARCH-QUEUE.md` | `14e4187a3320f4d77a70c796584b4be3d8ae0ea2` |
| REPLACE | `blueprints/verification/SNE-000F-RESULT-REGISTER.md` | `66bfa0a4334adaa2ff03d0400f7293af62f39acc` |
| ADD | `blueprints/verification/SNE-F00-BUILD-CLAIMS-REVIEW.md` | — |
| ADD | `blueprints/verification/SNE-F00-CANDIDATE-POLICY-REVIEW.md` | — |
| ADD | `blueprints/verification/SNE-F00-CLAIM-CATALOG.md` | — |
| ADD | `blueprints/verification/SNE-F00-DISSENT-RESOLUTION.md` | — |
| ADD | `blueprints/verification/SNE-F00-EVIDENCE-CHAIN.md` | — |
| ADD | `blueprints/verification/SNE-F00-GATE-IMPACT.md` | — |
| ADD | `blueprints/verification/SNE-F00-HANDOFF-PARSER-REVIEW.md` | — |
| ADD | `blueprints/verification/SNE-F00-NEXT-WORKORDER-ENTRY.md` | — |
| ADD | `blueprints/verification/SNE-F00-PIN-AND-BLOB-CHECKS.md` | — |
| ADD | `blueprints/verification/SNE-F00-PK3-VALIDATOR-REVIEW.md` | — |
| ADD | `blueprints/verification/SNE-F00-REVIEW-INTAKE.md` | — |
| ADD | `blueprints/verification/SNE-F00-REVIEWER-CHECKLIST.md` | — |
| ADD | `blueprints/verification/SNE-F00-SOURCE-SAMPLING.md` | — |
| ADD | `blueprints/verification/SNE-F00-SPRITE-PARSER-REVIEW.md` | — |
| ADD | `docs/SNE-F00-START-HERE.md` | — |
| ADD | `evidence/sources/SNE-F00-ENGINE-PRIMARY-OBSERVATIONS.md` | — |
| ADD | `evidence/sources/SNE-F00-GAME-PRIMARY-OBSERVATIONS.md` | — |
| ADD | `evidence/sources/SNE-F00-PIN-LEDGER.md` | — |
| REPLACE | `evidence/sources/SOURCE-INDEX.md` | `075cb7b54b9569145a5f8b069970bf65629702b1` |
| REPLACE | `governance/PHASE-00-REVIEW-GATES.md` | `84c299f6db19197bbc5c1f7a38eb39b8121a1d58` |
| ADD | `governance/SNE-F00-AUTHOR-FINDINGS.md` | — |
| ADD | `governance/SNE-F00-CONFLICT-OF-INTEREST.md` | — |
| ADD | `governance/SNE-F00-REVIEW-ASSIGNMENT.md` | — |
| ADD | `governance/SNE-F00-RISK-REGISTER.md` | — |
| REPLACE | `registry/PHASE-00-ARTIFACT-INDEX.md` | `3eb650c1de33397695b6a80febb053903e267b99` |
| ADD | `scaffold/SNE-F00-BUILD-VERIFICATION.json` | — |
| ADD | `scaffold/SNE-F00-CHANGELOG.md` | — |
| ADD | `scaffold/SNE-F00-MANIFEST.md` | — |
| ADD | `scaffold/SNE-F00-SHA256.json` | — |
| ADD | `templates/SNE-F00-CLAIM-REVIEW.json` | — |
| ADD | `templates/SNE-F00-INDEPENDENT-REVIEW.json` | — |
| ADD | `templates/SNE-F00-ISSUE-RECORD.json` | — |
| ADD | `templates/SNE-F00-OPERATOR-DECISION.json` | — |
| ADD | `templates/SNE-F00-README.md` | — |

## Operator conflict policy

If HEAD differs, worktree is not clean, any listed ADD path exists, or any REPLACE Git blob differs: **STOP**. No silent overwrite, wide `git add`, Git reset/clean, GitHub mutation or permission implied for builds/tests. Every changed file needs explicit staged inspection and the operator’s decision.
