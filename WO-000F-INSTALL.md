# SNE-WO-000F v0.8.0 — Overwrite-ready Windows installation and staging

## Safety checkpoint — BEFORE extraction

- Destination is `C:\` (**not** `C:\sovereign-nodes-engine`, or the archive would double nest).
- ZIP root is `sovereign-nodes-engine/`; all extracted files are Markdown/JSON.
- Required current clean local `HEAD`: `1644fb80c3e2803dd19465292423832e8fdf8e24`.
- Exact file inventory: **49 files — 43 ADD, 6 REPLACE**; see `scaffold/WO-000F-MANIFEST.md`.
- **No source code, proprietary IWAD, binary, .git, installer, game modification or network action is included.**
- STOP if HEAD differs, worktree is dirty from unrelated edits, an ADD path already exists, or a REPLACE blob preimage differs. Use manual 3-way review, not blind overwrite or force reset.

### Operator commands (read-only preflight)

```powershell
cd C:\sovereign-nodes-engine
git status --short
git rev-parse HEAD
```

The expected SHA is shown above. A *clean* result has no lines from `git status --short` before extraction. Consult exact REPLACE Git blob SHAs in the manifest and compare with `git rev-parse HEAD:<path>` if desired.

## Extract

Use Windows Explorer/7-Zip/PowerShell's extraction facility to unpack directly into `C:\`. This is file merging into the existing local repo; ZIP extraction itself does not check preimages. Do not overwrite a local modified/customized file without explicit review and backup.

## First post-extraction checks

```powershell
cd C:\sovereign-nodes-engine
git status --short
git diff --check
git diff --stat
```

The unstaged diff covers only tracked REPLACE files. New ADD files are untracked until staged. LF→CRLF warnings from Git on Windows are informational; actual `git diff --check` errors are not.

## Explicit path staging (no `git add -A`, no unscoped stage)

```powershell
git add -- `
  WO-000F-INSTALL.md `
  artifact-chain/acceptance/SNE-ACC-000F.md `
  artifact-chain/evidence/SNE-EVD-000F.md `
  artifact-chain/reconciliation/SNE-REC-000F.md `
  artifact-chain/verification/SNE-VER-000F.md `
  artifact-chain/work-orders/SNE-WO-000F.md `
  blueprints/architecture/SNE-000F-CLOSURE-ARCHITECTURE.md `
  blueprints/diagrams/SNE-000F-EVIDENCE-FLOW.md `
  blueprints/phases/PHASE-00-FOUNDATION.md `
  blueprints/research/RESEARCH-QUEUE.md `
  blueprints/research/SNE-000E-EVIDENCE-GAP-MATRIX.md `
  blueprints/verification/AGENTS.md `
  blueprints/verification/SNE-000F-ADMISSION-CHECKLIST.md `
  blueprints/verification/SNE-000F-BASELINE-IDENTITY.md `
  blueprints/verification/SNE-000F-BUILD-ENTRY-GATE.md `
  blueprints/verification/SNE-000F-CASE-TO-GATE-TRACE.md `
  blueprints/verification/SNE-000F-FALSE-POSITIVE-CONTROLS.md `
  blueprints/verification/SNE-000F-FIXTURE-ISOLATION.md `
  blueprints/verification/SNE-000F-HANDOFF-TESTS.md `
  blueprints/verification/SNE-000F-HARDWARE-TRIAL-MATRIX.md `
  blueprints/verification/SNE-000F-MAINTENANCE-LEGAL.md `
  blueprints/verification/SNE-000F-PK3-AND-WAD-GATES.md `
  blueprints/verification/SNE-000F-RESULT-REGISTER.md `
  blueprints/verification/SNE-000F-RESULT-SEMANTICS.md `
  blueprints/verification/SNE-000F-REVIEW-ROLES.md `
  blueprints/verification/SNE-000F-SPRITE-TESTS.md `
  blueprints/verification/SNE-000F-STOP-ROLLBACK.md `
  blueprints/verification/SNE-000F-SUBWORKORDER-ORDER.md `
  blueprints/verification/SNE-000F-WINDOWS-INVENTORY.md `
  docs/WO-000F-START-HERE.md `
  evidence/sources/SNE-000F-SOURCE-SNAPSHOT.md `
  evidence/sources/SNE-SRC-GAME-005.md `
  evidence/sources/SOURCE-INDEX.md `
  governance/PHASE-00-REVIEW-GATES.md `
  governance/WO-000F-AUTHORIZATION-MATRIX.md `
  governance/WO-000F-INDEPENDENT-REVIEW-HANDOFF.md `
  governance/WO-000F-REVIEW-FINDINGS.md `
  governance/WO-000F-RISK-REGISTER.md `
  registry/PHASE-00-ARTIFACT-INDEX.md `
  scaffold/WO-000F-BUILD-VERIFICATION.json `
  scaffold/WO-000F-CHANGELOG.md `
  scaffold/WO-000F-FILE-SHA256.json `
  scaffold/WO-000F-MANIFEST.md `
  templates/SNE-000F-AUTHORIZATION.json `
  templates/SNE-000F-CASE-RESULT.json `
  templates/SNE-000F-DEFECT-DISPOSITION.json `
  templates/SNE-000F-GATE-LEDGER.json `
  templates/SNE-000F-README.md `
  templates/SNE-000F-REVIEW-RESULT.json
```

## Complete staged verification

```powershell
git diff --cached --check
git diff --cached --stat
git diff --cached --name-only
```

Expected: zero whitespace errors and **49 exact staged paths**. Inspect the full staged diff and compare against manifest; staging isn't approval to change canonical game or engine repos. Do not run game builds or GPU tests just because the plans contain future procedures.

## Publication (operator manual only)

Only if local staged checks pass and files are approved:

```powershell
git commit -m "docs: prepare SNE-WO-000F evidence closure readiness"
git push origin main
```

Record the actual resulting commit SHA after publishing in a future reconciliation update. WO-F commits **documentation readiness**, not P00-G1…G8 closure, test execution or foundation selection.
