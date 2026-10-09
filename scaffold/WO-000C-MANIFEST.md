# SNE-WO-000C v0.5.0 — Explicit archive manifest

- Root inside ZIP: `sovereign-nodes-engine/`
- Intended extraction: `C:\` only (merges into `C:\sovereign-nodes-engine`)
- Required clean Git HEAD: `edc274f320cbd891c1f7fcef80f308562c0067ef`
- Action breakdown: **8 REPLACE**, **31 ADD**, **39 total**.
- Contents: research-only Markdown and JSON. No implementation files, engines, WADs, `.git`, deletions, keys, or genealogy.
- Preimages: Git blob SHA-1 from pinned engine-scaffold commit, captured before package generation. Local file hash is not checked automatically when unzipping; operator must verify baseline/dirty-state first.
- Archive hashes: SHA-256 of member uncompressed bytes for every file except the checksum ledger itself, listed in `scaffold/WO-000C-FILE-SHA256.json`.
- Validation: `scaffold/WO-000C-BUILD-VERIFICATION.json`. Archive verification is not game runtime verification.

## Exact paths and intentional actions

| Action | Repo-relative path | Expected existing Git blob SHA-1 |
|---|---|---|
| ADD | `WO-000C-INSTALL.md` | — |
| ADD | `artifact-chain/acceptance/SNE-ACC-000C.md` | — |
| ADD | `artifact-chain/evidence/SNE-EVD-000C.md` | — |
| ADD | `artifact-chain/reconciliation/SNE-REC-000C.md` | — |
| ADD | `artifact-chain/verification/SNE-VER-000C.md` | — |
| REPLACE | `artifact-chain/work-orders/SNE-WO-000C.md` | `e3f22e093a1b334bade00561033f373b3ac1dd05` |
| ADD | `blueprints/architecture/SNE-000C-ARCHITECTURE.md` | — |
| ADD | `blueprints/diagrams/SNE-000C-TRACE-FLOW.md` | — |
| ADD | `blueprints/diagrams/SNE-000C-ZONE-FLOW.md` | — |
| REPLACE | `blueprints/interfaces/IF-SNE-001-GAME-COMPAT.md` | `32a64c5039338b48acbfd86269eb37db74692b82` |
| REPLACE | `blueprints/interfaces/IF-SNE-003-WORLD-TRANSITION.md` | `bf406eb8f7968fe5d33078296ca3e838998f182f` |
| REPLACE | `blueprints/research/COMPATIBILITY-TEST-MATRIX.md` | `da6a3fccc91a2bab7bf1136b6b26547cddbd6ddc` |
| REPLACE | `blueprints/research/HARDWARE-BENCHMARK-PLAN.md` | `242137205c51457bfea177b85a8dea16c1706317` |
| REPLACE | `blueprints/research/RESEARCH-QUEUE.md` | `b33527252e9dd3f09d0d0a9d24789ba200233c3a` |
| ADD | `blueprints/research/SNE-000C-EFFORT-ESTIMATES.md` | — |
| ADD | `blueprints/research/SNE-000C-ENGINE-LANES.md` | — |
| ADD | `blueprints/research/SNE-000C-FEATURE-TRACE.md` | — |
| ADD | `blueprints/research/SNE-000C-HANDOFF-HARDENING.md` | — |
| ADD | `blueprints/research/SNE-000C-LIGHTING-BUDGET.md` | — |
| ADD | `blueprints/research/SNE-000C-OPEN-QUESTIONS.md` | — |
| ADD | `blueprints/research/SNE-000C-PERFORMANCE-PROFILES.md` | — |
| ADD | `blueprints/research/SNE-000C-TEST-CASE-CATALOG.md` | — |
| ADD | `blueprints/research/SNE-000C-VOXEL-GLTF.md` | — |
| ADD | `blueprints/research/SNE-000C-WORLD-CONTINUITY.md` | — |
| ADD | `blueprints/research/SNE-000C-ZSCRIPT-PACKAGING.md` | — |
| ADD | `docs/WO-000C-START-HERE.md` | — |
| ADD | `evidence/sources/SNE-000C-PIN-LEDGER.md` | — |
| ADD | `evidence/sources/SNE-SRC-BIASEDDOOM-003.md` | — |
| ADD | `evidence/sources/SNE-SRC-GAME-003.md` | — |
| ADD | `evidence/sources/SNE-SRC-GZDOOM-003.md` | — |
| ADD | `evidence/sources/SNE-SRC-UZDOOM-003.md` | — |
| REPLACE | `evidence/sources/SOURCE-INDEX.md` | `c25e7ed3d3d91e22ba78f209fe2a2e460c073476` |
| ADD | `governance/WO-000C-REVIEW-FINDINGS.md` | — |
| ADD | `governance/WO-000C-RISK-REGISTER.md` | — |
| REPLACE | `registry/PHASE-00-ARTIFACT-INDEX.md` | `3ae0ce3f3eccdea724a82d16355d6be87dc8fa31` |
| ADD | `scaffold/WO-000C-BUILD-VERIFICATION.json` | — |
| ADD | `scaffold/WO-000C-CHANGELOG.md` | — |
| ADD | `scaffold/WO-000C-FILE-SHA256.json` | — |
| ADD | `scaffold/WO-000C-MANIFEST.md` | — |

## Safety and rollback

If local HEAD differs or any ADD already exists: **STOP**. Do not destructively merge. Read-only design-only package. After extraction, inspect all added files and replacements, then stage explicit paths only. Verify new files as well as replacements with `git diff --cached --check`. Commit/push only after the operator confirms the diff. No engine technical gate becomes PASS due to this ZIP.
