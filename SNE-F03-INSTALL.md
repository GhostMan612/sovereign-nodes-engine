# SNE-F03 v1.2.0 — Operator installation and Git publication

**STOP if conditions fail.** Package contains only documentation/JSON; no actual build or computer access is authorized.

## 0. Before extraction: check exact baseline and tree

```powershell
cd C:\sovereign-nodes-engine
git status --short
git rev-parse HEAD
```

Expected **no status output**, HEAD **`f2f2cfec676b9a5254fa2a5a7e6f08198581fa09`**. A wrong commit, staged content or any unrelated dirty/untracked file means STOP. Before extracting, check each REPLACE blob SHA-1 from `scaffold/SNE-F03-MANIFEST.md` against `git rev-parse "HEAD:path"` and ensure every ADD path is absent. Do not replace an operator-customized file just because its name matches.

## 1. Extract

Unzip to **`C:\`**, preserving archive's `sovereign-nodes-engine/` prefix. Do **not** extract the prefix inside `C:\sovereign-nodes-engine`; that would double-nest. Select overwrite only for six expected REPLACE preimages after verifying no local modifications.

## 2. Inspect working tree

```powershell
cd C:\sovereign-nodes-engine
git status --short
git diff --check
git diff --stat
```

Expected **6 modified** tracked docs + **43 untracked** new docs/JSON (Git may collapse new directories). `git diff --stat` shows tracked REPLACE files only until staging; LF→CRLF warnings on Windows are informational if `git diff --check` reports no errors.

## 3. Stage ONLY the 49 manifest paths

```powershell
git add -- `
  SNE-F03-INSTALL.md `
  artifact-chain/acceptance/SNE-ACC-F03.md `
  artifact-chain/evidence/SNE-EVD-F03.md `
  artifact-chain/reconciliation/SNE-REC-F03.md `
  artifact-chain/verification/SNE-VER-F03.md `
  artifact-chain/work-orders/SNE-WO-F03.md `
  blueprints/architecture/SNE-F03-BUILD-BOUNDARY.md `
  blueprints/diagrams/SNE-F03-BUILD-GATE-GRAPH.md `
  blueprints/phases/PHASE-00-FOUNDATION.md `
  blueprints/research/RESEARCH-QUEUE.md `
  blueprints/verification/SNE-000F-RESULT-REGISTER.md `
  blueprints/verification/SNE-F03-ADMISSION.md `
  blueprints/verification/SNE-F03-BIASEDDOOM-EXPERIMENT.md `
  blueprints/verification/SNE-F03-BUILD-FAILURE-TAXONOMY.md `
  blueprints/verification/SNE-F03-CMAKE-CONFIGURATION.md `
  blueprints/verification/SNE-F03-COMMAND-PLAN.md `
  blueprints/verification/SNE-F03-DEPENDENCY-DRIFT.md `
  blueprints/verification/SNE-F03-DEPENDENCY-SBOM.md `
  blueprints/verification/SNE-F03-F04-ENTRY.md `
  blueprints/verification/SNE-F03-GENERATOR-MATRIX.md `
  blueprints/verification/SNE-F03-GZDOOM-CONTROL.md `
  blueprints/verification/SNE-F03-OPERATOR-HANDOFF.md `
  blueprints/verification/SNE-F03-RED-FLAGS.md `
  blueprints/verification/SNE-F03-REPRODUCIBILITY-TRIALS.md `
  blueprints/verification/SNE-F03-RESOURCE-HASHES.md `
  blueprints/verification/SNE-F03-SECURITY-AND-LEGAL.md `
  blueprints/verification/SNE-F03-SOURCE-IMMUTABILITY.md `
  blueprints/verification/SNE-F03-STOP-ROLLBACK.md `
  blueprints/verification/SNE-F03-UZDOOM-COMPARATOR.md `
  blueprints/verification/SNE-F03-WINDOWS-TOOLCHAIN.md `
  docs/SNE-F03-START-HERE.md `
  evidence/sources/SNE-F03-CMAKE-OBSERVATIONS.md `
  evidence/sources/SNE-F03-SOURCE-PINS.md `
  evidence/sources/SOURCE-INDEX.md `
  governance/PHASE-00-REVIEW-GATES.md `
  governance/SNE-F03-AUTHOR-REVIEW.md `
  governance/SNE-F03-AUTHORIZATION-REQUEST.md `
  governance/SNE-F03-RISK-REGISTER.md `
  registry/PHASE-00-ARTIFACT-INDEX.md `
  scaffold/SNE-F03-BUILD-VERIFICATION.json `
  scaffold/SNE-F03-CHANGELOG.md `
  scaffold/SNE-F03-MANIFEST.md `
  scaffold/SNE-F03-SHA256.json `
  templates/SNE-F03-BUILD-RECORD.json `
  templates/SNE-F03-DEPENDENCY-ROW.json `
  templates/SNE-F03-HOST-READINESS.json `
  templates/SNE-F03-README.md `
  templates/SNE-F03-REPRO-RECORD.json `
  templates/SNE-F03-RESOURCE-RECORD.json
```

## 4. Verify stage before commit

```powershell
git diff --cached --check
git diff --cached --stat
git diff --cached --name-only
git diff --cached --name-only | Measure-Object -Line
git diff --cached --diff-filter=D --name-only
```

Expected **49 staged paths, 43 additions, 6 modifications**, no unexpected deletes, no whitespace errors. Review `git diff --cached` for accidental private details, changed historical claims or executable file additions. Reconcile mismatch manually.

## 5. Operator-controlled commit/push (only after PASS)

```powershell
git commit -m "docs: complete SNE-F03 native Windows build readiness"
git push origin main
git log -1 --oneline
git status --short
git rev-parse HEAD
```

Commit/push changes only planning documentation; do not treat it as engine build approval, test outcome, reviewer signoff, or selected foundation. Preserve resulting full SHA as next planning baseline. All `AUTH-…` execution categories are still unapproved unless separately signed/authenticated under F-01.

## Stop/recovery

If any file/canonical repo changed unexpectedly, stop. Inspect manifest and staged diff; no force reset, git clean, broad stage, or auto-overwrite. Future recovery uses deliberate, individual-file review under operator control.
