# SNE Phase 00 v0.2.0 — explicit overlay manifest

- Target: `C:\sovereign-nodes-engine` via extraction to `C:\`.
- Base: SNE scaffold v0.1.0 (`scaffold/MANIFEST.md`).
- Archive prefix: `sovereign-nodes-engine/`.
- Contents: documentation-only. No deletes. No source code. No `.git/`.
- Only the following path is intentionally **REPLACED**: `blueprints/phases/PHASE-00-FOUNDATION.md`.
- All remaining files are new **ADDITIONS**. If any addition path already exists locally, treat it as a conflict rather than overwriting silently.
- Generated file list and checksums: `scaffold/PHASE-00-FILE-SHA256.json`.

## Exact file list

| Action | Path |
|---|---|
| ADD | `sovereign-nodes-engine/PHASE-00-INSTALL.md` |
| ADD | `sovereign-nodes-engine/artifact-chain/acceptance/SNE-ACC-000.md` |
| ADD | `sovereign-nodes-engine/artifact-chain/blueprints/SNE-BP-000.md` |
| ADD | `sovereign-nodes-engine/artifact-chain/decisions/SNE-DEC-000.md` |
| ADD | `sovereign-nodes-engine/artifact-chain/evidence/SNE-EVD-000.md` |
| ADD | `sovereign-nodes-engine/artifact-chain/intake/SNE-INT-000.md` |
| ADD | `sovereign-nodes-engine/artifact-chain/reconciliation/SNE-REC-000.md` |
| ADD | `sovereign-nodes-engine/artifact-chain/verification/SNE-VER-000.md` |
| ADD | `sovereign-nodes-engine/artifact-chain/work-orders/SNE-WO-000A.md` |
| ADD | `sovereign-nodes-engine/artifact-chain/work-orders/SNE-WO-000B.md` |
| ADD | `sovereign-nodes-engine/artifact-chain/work-orders/SNE-WO-000C.md` |
| ADD | `sovereign-nodes-engine/artifact-chain/work-orders/SNE-WO-000D.md` |
| ADD | `sovereign-nodes-engine/artifact-chain/work-orders/SNE-WO-000E.md` |
| ADD | `sovereign-nodes-engine/blueprints/decisions/ADR-SNE-002-FOUNDATION-PENDING.md` |
| ADD | `sovereign-nodes-engine/blueprints/interfaces/IF-SNE-001-GAME-COMPAT.md` |
| ADD | `sovereign-nodes-engine/blueprints/interfaces/IF-SNE-002-MANTLE-SNAPSHOT.md` |
| ADD | `sovereign-nodes-engine/blueprints/interfaces/IF-SNE-003-WORLD-TRANSITION.md` |
| REPLACE | `sovereign-nodes-engine/blueprints/phases/PHASE-00-FOUNDATION.md` |
| ADD | `sovereign-nodes-engine/blueprints/research/CANDIDATE-MATRIX.md` |
| ADD | `sovereign-nodes-engine/blueprints/research/COMPATIBILITY-TEST-MATRIX.md` |
| ADD | `sovereign-nodes-engine/blueprints/research/DEPENDENCY-LICENSE-MATRIX.md` |
| ADD | `sovereign-nodes-engine/blueprints/research/HARDWARE-BENCHMARK-PLAN.md` |
| ADD | `sovereign-nodes-engine/blueprints/research/RESEARCH-QUEUE.md` |
| ADD | `sovereign-nodes-engine/blueprints/research/SECURITY-BOUNDARIES.md` |
| ADD | `sovereign-nodes-engine/blueprints/research/SOVEREIGN-NODES-INVENTORY.md` |
| ADD | `sovereign-nodes-engine/blueprints/research/UPSTREAM-CODE-MAP.md` |
| ADD | `sovereign-nodes-engine/docs/PHASE-00-START-HERE.md` |
| ADD | `sovereign-nodes-engine/evidence/sources/SOURCE-INDEX.md` |
| ADD | `sovereign-nodes-engine/governance/PHASE-00-REVIEW-GATES.md` |
| ADD | `sovereign-nodes-engine/governance/PHASE-00-RISKS.md` |
| ADD | `sovereign-nodes-engine/registry/PHASE-00-ARTIFACT-INDEX.md` |
| ADD | `sovereign-nodes-engine/scaffold/PHASE-00-CHANGELOG.md` |
| ADD | `sovereign-nodes-engine/verification/PHASE-00-VERIFICATION-PLAN.md` |

**Do not auto-delete or recreate the repository. Inspect `git diff` before committing.**
