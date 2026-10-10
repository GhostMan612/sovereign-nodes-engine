# SNE-F02 v1.1.0 — Exact overwrite installation and verification

## 0. STOP / source checks

Only install into the expected original clean local repo `C:\sovereign-nodes-engine` at exactly `725fded39c0d50139ab76182211e32375bc2764e`. If other work is present, keep it intact and **do not extract**; reconcile first. Never run `git reset --hard`, `git clean`, `git add .`, or force push.

```powershell
cd C:\sovereign-nodes-engine
git status --short
git rev-parse HEAD
```

Confirm all six tracked REPLACE paths exactly match the Git blob SHA-1s in `scaffold/SNE-F02-MANIFEST.md` and that every ADD path is absent before extraction. Example read-only preimage for one tracked file:

```powershell
git hash-object -- blueprints/phases/PHASE-00-FOUNDATION.md
```

For every replacement, compare the hash value with the manifest's exact row. Stop on mismatch; `git status --short` alone is not a blob proof. The package author did not inspect operator's local disk.

## 1. Extract

ZIP root is `sovereign-nodes-engine/`. Extract the ZIP **into `C:\`**, not into the inner project folder (avoid nested duplicate). Enable overwrite only after matching the exact clean base and all ADD/REPLACE checks.

## 2. Inspect *all* changes

```powershell
cd C:\sovereign-nodes-engine
git status --short
git diff --check
git diff --stat
```

Expected: `6` tracked modified files and `39` new files. LF→CRLF advisory warnings under Windows are harmless if `git diff --check` finds no actual errors. Untracked additions do not enter `git diff --check` until staged.

## 3. Explicitly stage exactly 45 files

```powershell
git add -- `
  SNE-F02-INSTALL.md `
  artifact-chain/acceptance/SNE-ACC-F02.md `
  artifact-chain/evidence/SNE-EVD-F02.md `
  artifact-chain/reconciliation/SNE-REC-F02.md `
  artifact-chain/verification/SNE-VER-F02.md `
  artifact-chain/work-orders/SNE-WO-F02.md `
  blueprints/architecture/SNE-F02-BASELINE-CONTRACT.md `
  blueprints/diagrams/SNE-F02-EVIDENCE-FLOW.md `
  blueprints/phases/PHASE-00-FOUNDATION.md `
  blueprints/research/RESEARCH-QUEUE.md `
  blueprints/verification/SNE-000F-RESULT-REGISTER.md `
  blueprints/verification/SNE-F02-ADMISSION.md `
  blueprints/verification/SNE-F02-AUTH-DISPATCH.md `
  blueprints/verification/SNE-F02-EVIDENCE-QUALITY.md `
  blueprints/verification/SNE-F02-F03-ENTRY-GATE.md `
  blueprints/verification/SNE-F02-FIXTURE-DELTA.md `
  blueprints/verification/SNE-F02-GAME-VS-ENGINE.md `
  blueprints/verification/SNE-F02-GAPNODE-CONTROL.md `
  blueprints/verification/SNE-F02-GLDEFS-MATRIX.md `
  blueprints/verification/SNE-F02-HANDOFF-ADVERSARIAL.md `
  blueprints/verification/SNE-F02-HANDOFF-BOOLEAN.md `
  blueprints/verification/SNE-F02-HOST-INVENTORY.md `
  blueprints/verification/SNE-F02-IDENTITY-AND-CHECKSUM.md `
  blueprints/verification/SNE-F02-INDEPENDENT-REVIEW.md `
  blueprints/verification/SNE-F02-PK3-STRUCTURE.md `
  blueprints/verification/SNE-F02-SPRITE-ALIAS-MATRIX.md `
  blueprints/verification/SNE-F02-VALIDATOR-PATH.md `
  blueprints/verification/SNE-F02-WAD-VALIDATION.md `
  docs/SNE-F02-START-HERE.md `
  evidence/sources/SNE-F02-PRIMARY-SOURCE-NOTES.md `
  evidence/sources/SOURCE-INDEX.md `
  governance/PHASE-00-REVIEW-GATES.md `
  governance/SNE-F02-AUTHOR-FINDINGS.md `
  governance/SNE-F02-AUTHORIZATION-REQUESTS.md `
  governance/SNE-F02-RISK-REGISTER.md `
  registry/PHASE-00-ARTIFACT-INDEX.md `
  scaffold/SNE-F02-BUILD-VERIFICATION.json `
  scaffold/SNE-F02-CHANGELOG.md `
  scaffold/SNE-F02-MANIFEST.md `
  scaffold/SNE-F02-SHA256.json `
  templates/SNE-F02-BASELINE-IDENTITY.json `
  templates/SNE-F02-CASE-RESULT.json `
  templates/SNE-F02-FIXTURE-CONTROL.json `
  templates/SNE-F02-HOST-INVENTORY.json `
  templates/SNE-F02-PK3-CHECK.json
```

## 4. Final staged validation

```powershell
git diff --cached --check
git diff --cached --stat
git diff --cached --name-only
git diff --cached --name-only | Measure-Object -Line
git diff --cached
```

Expected count `45` and no whitespace issues, unexpected delete or unrelated edit. Review the complete staged diff before publishing.

## 5. Operator-only commit/push (after reviewing stage)

```powershell
git commit -m "docs: complete SNE-F02 baseline inventory and fixture verification blueprint"
git push origin main
git log -1 --oneline
git status --short
git rev-parse HEAD
```

If any file is unexpectedly present or SHA doesn't match: stop and perform manual reconciliation; do not use bulk cleanup. Document publication **does not grant AUTH-H/F/T**, close G1–G8, prove runtime behavior or authorize Phase 01. Future real data, signatures and full proprietary assets stay outside public Git.
