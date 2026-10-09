# SNE-WO-000A v0.3.0 — overlay installation and operator review

**Target:** `C:\sovereign-nodes-engine`
**Extract to:** `C:\` (ZIP already contains `sovereign-nodes-engine/`)
**Baseline:** `main` at `317e360c041ce3e02dbef7634085cf687f84c02b`
**Type:** documentation/research only; **NO `.git`**, binaries, IWADs, scripts or engine source.
**State:** source-inspection evidence gathered; review and all runtime tests pending.

## Before extraction

1. Ensure local modifications are committed/stashed or reviewed. Do not blindly overwrite edited files.
2. Review the exact REPLACE and ADD paths and baseline Git blob hashes in `scaffold/WO-000A-MANIFEST.md`.
3. Make a copy of any locally customized file listed under REPLACE. Extraction overwrites only files whose names collide.
4. Extract the ZIP to `C:\`, not into the repository directory.

## After extraction (PowerShell, operator controlled)

```powershell
cd C:\sovereign-nodes-engine
git status --short
git diff --check
git diff --stat
git diff -- artifact-chain/work-orders/SNE-WO-000A.md blueprints/research/SOVEREIGN-NODES-INVENTORY.md
git status --short
```

**Do not use `git add -A` for this project:** stage only the intended paths after reviewing the overlay. This package intentionally does not contain automation scripts or execute commands. The operator performs and authorizes any commit/push.

## Reading order

1. `docs/WO-000A-START-HERE.md`
2. `artifact-chain/evidence/SNE-EVD-000A.md`
3. `blueprints/research/SOVEREIGN-NODES-INVENTORY.md`
4. `blueprints/research/UPSTREAM-CODE-MAP.md`
5. `governance/WO-000A-REVIEW-FINDINGS.md`
6. `artifact-chain/verification/SNE-VER-000A.md`

**Stop condition:** Do not mark Phase 00 complete or authorize Phase 01 merely from these source observations.
