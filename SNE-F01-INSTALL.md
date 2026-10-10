# SNE-F01 v1.0.0 — Safe local ZIP merge and 42-path Git staging

**Content:** Markdown/JSON only: exactly 42 files (37 ADD, 5 REPLACE). Archive contains root `sovereign-nodes-engine/`.
**Required exact clean repository HEAD before merge:** `148dc28cdbdf4970c8011d76762b31b8dcafea0b`.
**Destination:** unzip into `C:\` (not directly into `C:\sovereign-nodes-engine` or it will double-nest).

## 1. Before extraction — mandatory guard

```powershell
cd C:\sovereign-nodes-engine
git branch --show-current
git status --short
git rev-parse HEAD
```

Require branch `main`, empty `git status --short`, and exact HEAD above. Otherwise **STOP** and review, do not run `reset --hard`, `clean`, or overwrite dirty files. Check 5 REPLACE blob values against `scaffold/SNE-F01-MANIFEST.md` in the ZIP and confirm 37 ADD paths do not already exist locally. Source ZIP preimage hashes are not authority to destroy local changes.

## 2. Merge/extract to `C:\`

Use the normal Windows ZIP extractor with destination `C:\`. The extracted archive root is `sovereign-nodes-engine/`, so its relative documents land in the correct subfolders.

## 3. Unstaged verification

```powershell
cd C:\sovereign-nodes-engine
git status --short
git diff --check
git diff --stat
```

Expect exactly five tracked modifications plus 37 new files (Git may group new files as untracked directories). No unexpected removals. LF-to-CRLF warnings on Windows are informational, but actual whitespace errors must be investigated.

## 4. Explicit-path staging (ALL 42, no wildcards)

```powershell
git add -- `
  SNE-F01-INSTALL.md `
  artifact-chain/acceptance/SNE-ACC-F01.md `
  artifact-chain/evidence/SNE-EVD-F01.md `
  artifact-chain/reconciliation/SNE-REC-F01.md `
  artifact-chain/verification/SNE-VER-F01.md `
  artifact-chain/work-orders/SNE-WO-F01.md `
  blueprints/architecture/SNE-F01-SCOPE-BOUNDARIES.md `
  blueprints/diagrams/SNE-F01-AUTHORIZATION-LIFECYCLE.md `
  blueprints/phases/PHASE-00-FOUNDATION.md `
  blueprints/research/RESEARCH-QUEUE.md `
  blueprints/verification/SNE-F01-AGENT-DISPATCH-CONTRACT.md `
  blueprints/verification/SNE-F01-AUTHORIZATION-LIFECYCLE.md `
  blueprints/verification/SNE-F01-BUILD-RUN-LANES.md `
  blueprints/verification/SNE-F01-DEPENDENCY-NETWORK-CONTROLS.md `
  blueprints/verification/SNE-F01-EVIDENCE-CHAIN-AND-RETENTION.md `
  blueprints/verification/SNE-F01-F02-ENTRY-GATE.md `
  blueprints/verification/SNE-F01-FIXTURE-LANE.md `
  blueprints/verification/SNE-F01-HOST-INVENTORY-LANE.md `
  blueprints/verification/SNE-F01-PATH-DATA-BOUNDARIES.md `
  blueprints/verification/SNE-F01-PERFORMANCE-ADMISSION.md `
  blueprints/verification/SNE-F01-READ-ONLY-REVIEW-LANE.md `
  blueprints/verification/SNE-F01-SCOPE-FREEZE.md `
  blueprints/verification/SNE-F01-STOP-REVOKE-ROLLBACK.md `
  docs/SNE-F01-START-HERE.md `
  governance/PHASE-00-REVIEW-GATES.md `
  governance/SNE-F01-AUTHOR-REVIEW.md `
  governance/SNE-F01-DECISION-LOG.md `
  governance/SNE-F01-INDEPENDENCE-APPOINTMENT.md `
  governance/SNE-F01-RISK-REGISTER.md `
  governance/WO-000F-AUTHORIZATION-MATRIX.md `
  registry/PHASE-00-ARTIFACT-INDEX.md `
  scaffold/SNE-F01-BUILD-VERIFICATION.json `
  scaffold/SNE-F01-CHANGELOG.md `
  scaffold/SNE-F01-MANIFEST.md `
  scaffold/SNE-F01-SHA256.json `
  templates/SNE-F01-AUTHORIZATION.json `
  templates/SNE-F01-AUTHORIZATION.schema.json `
  templates/SNE-F01-CHANGE-REQUEST.json `
  templates/SNE-F01-README.md `
  templates/SNE-F01-REVIEW-ATTESTATION.json `
  templates/SNE-F01-REVOCATION.json `
  templates/SNE-F01-SCOPE-FREEZE.json
```

## 5. Staged verification; stop on unexpected changes

```powershell
git diff --cached --check
git diff --cached --stat
git diff --cached --name-only
git diff --cached --name-status
```

Expect 42 staged files, 5 `M` plus 37 `A`, no `D`. Inspect the staged diff and any local custom work before proceeding. `git diff --check` without `--cached` does not cover untracked files; this final staged check is mandatory.

## 6. Operator-only commit and publication (after checks pass)

```powershell
git commit -m "docs: prepare SNE-F01 operator authorization scope freeze"
git push origin main
git log -1 --oneline
git rev-parse HEAD
git status --short
```

The resulting commit SHA is deliberately not predicted. Record it only after a successful local push. This author did not mutate GitHub.

## Recovery and safety

On any mismatch, **STOP** and compare the manifest, exact source blobs and local diff; preserve unrelated changes. Do not bulk delete/reset. If extraction to wrong directory caused duplicate nesting, first inspect all affected paths and move only the known overlay files after operator review. Unzipping/staging/pushing these forms **does not** approve any review, host inventory, fixture, native build, gameplay run, GPU benchmark, distribution, source edit, engine selection or Phase 01 work. All request objects begin `PROPOSED` and require a distinct private operator decision before later execution.
