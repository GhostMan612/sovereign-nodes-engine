# WO-000C v0.5.0 — Safe overlay installation

- Target repository: `C:\sovereign-nodes-engine`
- Extract destination: `C:\` (ZIP contains top-level `sovereign-nodes-engine/`)
- Required clean HEAD: `edc274f320cbd891c1f7fcef80f308562c0067ef` (`edc274f`)
- Scope: Markdown/JSON only. No engine source, runnable scripts, binaries, commercial IWADs, hidden genealogy, `.git/`, remote writes, deletes or refactors.
- Overwrite scope: only 8 **REPLACE** paths explicitly listed in `scaffold/WO-000C-MANIFEST.md` and their expected original Git blob SHA-1 identities.
- Other paths are **ADD**: if any exists locally, stop and resolve before extracting.

## Workflow

1. Confirm `git status --short` is empty and `git rev-parse HEAD` is the full SHA above. Do not proceed on a dirty tree.
2. Read `scaffold/WO-000C-MANIFEST.md` and `scaffold/WO-000C-FILE-SHA256.json` inside ZIP before granting overwrite permissions. Back up any local customization.
3. Extract ZIP to `C:\`. Never extract into `C:\sovereign-nodes-engine\`, which would double-nest the root.
4. Inspect `git status --short`, `git diff --check` and `git diff --stat`. These exclude untracked-file whitespace inspection.
5. Stage **only** the explicit 39 file paths in the manifest; no `git add -A`, `git add .`, automatic push or force-push.
6. Inspect `git diff --cached --check` and `git diff --cached --stat` including additions. Any staged error blocks commit. Do not trim shipped Markdown without updating its checksums; contact package author for corrected ZIP.
7. Commit and push manually only after accepting the staged diff. Git success does **not** mean runtime tests or Phase 00 acceptance have passed.

## Rollback

Before committing, revert only the intended changes if needed, taking care not to destroy personal/unrelated edits. After commit, use a separately reviewed revert commit. Never reset or force-push as a shortcut. Independent audit trail stays intact.
## Explicit staging after operator review

Never use `git add .` or `git add -A`. If any path is unexpected or a local edit conflicts, stop. Only after inspecting the extracted overlay, run:

```powershell
git add -- `
  WO-000C-INSTALL.md `
  artifact-chain/acceptance/SNE-ACC-000C.md `
  artifact-chain/evidence/SNE-EVD-000C.md `
  artifact-chain/reconciliation/SNE-REC-000C.md `
  artifact-chain/verification/SNE-VER-000C.md `
  artifact-chain/work-orders/SNE-WO-000C.md `
  blueprints/architecture/SNE-000C-ARCHITECTURE.md `
  blueprints/diagrams/SNE-000C-TRACE-FLOW.md `
  blueprints/diagrams/SNE-000C-ZONE-FLOW.md `
  blueprints/interfaces/IF-SNE-001-GAME-COMPAT.md `
  blueprints/interfaces/IF-SNE-003-WORLD-TRANSITION.md `
  blueprints/research/COMPATIBILITY-TEST-MATRIX.md `
  blueprints/research/HARDWARE-BENCHMARK-PLAN.md `
  blueprints/research/RESEARCH-QUEUE.md `
  blueprints/research/SNE-000C-EFFORT-ESTIMATES.md `
  blueprints/research/SNE-000C-ENGINE-LANES.md `
  blueprints/research/SNE-000C-FEATURE-TRACE.md `
  blueprints/research/SNE-000C-HANDOFF-HARDENING.md `
  blueprints/research/SNE-000C-LIGHTING-BUDGET.md `
  blueprints/research/SNE-000C-OPEN-QUESTIONS.md `
  blueprints/research/SNE-000C-PERFORMANCE-PROFILES.md `
  blueprints/research/SNE-000C-TEST-CASE-CATALOG.md `
  blueprints/research/SNE-000C-VOXEL-GLTF.md `
  blueprints/research/SNE-000C-WORLD-CONTINUITY.md `
  blueprints/research/SNE-000C-ZSCRIPT-PACKAGING.md `
  docs/WO-000C-START-HERE.md `
  evidence/sources/SNE-000C-PIN-LEDGER.md `
  evidence/sources/SNE-SRC-BIASEDDOOM-003.md `
  evidence/sources/SNE-SRC-GAME-003.md `
  evidence/sources/SNE-SRC-GZDOOM-003.md `
  evidence/sources/SNE-SRC-UZDOOM-003.md `
  evidence/sources/SOURCE-INDEX.md `
  governance/WO-000C-REVIEW-FINDINGS.md `
  governance/WO-000C-RISK-REGISTER.md `
  registry/PHASE-00-ARTIFACT-INDEX.md `
  scaffold/WO-000C-BUILD-VERIFICATION.json `
  scaffold/WO-000C-CHANGELOG.md `
  scaffold/WO-000C-FILE-SHA256.json `
  scaffold/WO-000C-MANIFEST.md
```

Then run `git diff --cached --check`, `git diff --cached --stat` and `git status --short` before manually committing/pushing.
