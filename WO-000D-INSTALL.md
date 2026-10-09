# WO-000D v0.6.0 — Safe local installation and verification

**Archive root:** `sovereign-nodes-engine/`.
**Extraction destination:** `C:\` (**not** `C:\sovereign-nodes-engine`, which would double-nest).
**Required exact HEAD before installation:** `706db57a4fbabd701244dd9e4674a59f7ab044f3`.
**Authorized content:** 45 documentation/JSON files: 7 REPLACE and 38 ADD. ZIP contains no executable/scripts, engine source, WAD/IWADs or `.git`.

## PRE-EXTRACTION guard — execute before overwriting anything

```powershell
cd C:\sovereign-nodes-engine
git status --short
git rev-parse HEAD
```

`git status --short` must be empty, and HEAD must be exactly `706db57a4fbabd701244dd9e4674a59f7ab044f3`. If not, **STOP**. Read `scaffold/WO-000D-MANIFEST.md` before extraction; its seven expected source blob IDs are the explicit overwrite guard. Inspect any local customization; ZIP extraction is not a Git merge. If ZIP has already been extracted, do not treat modified status as evidence that pre-extraction state was clean.

## POST-EXTRACTION check

```powershell
cd C:\sovereign-nodes-engine
git status --short
git diff --check
git diff --stat
```

`git diff --stat` initially lists only 7 tracked replacements, **not** the 38 untracked additions. LF→CRLF warnings under Windows are not Git whitespace errors.

## Explicit staging — all member paths and no wildcard

```powershell
$wo000dPaths = @(
  "WO-000D-INSTALL.md"
  "artifact-chain/acceptance/SNE-ACC-000D.md"
  "artifact-chain/evidence/SNE-EVD-000D.md"
  "artifact-chain/reconciliation/SNE-REC-000D.md"
  "artifact-chain/verification/SNE-VER-000D.md"
  "artifact-chain/work-orders/SNE-WO-000D.md"
  "blueprints/architecture/SNE-000D-EXECUTION-BOUNDARY.md"
  "blueprints/diagrams/SNE-000D-REPRODUCIBILITY-FLOW.md"
  "blueprints/research/DEPENDENCY-LICENSE-MATRIX.md"
  "blueprints/research/HARDWARE-BENCHMARK-PLAN.md"
  "blueprints/research/RESEARCH-QUEUE.md"
  "blueprints/research/SNE-000B-COMPILER-BUILD-MATRIX.md"
  "blueprints/research/SNE-000D-ARTIFACT-PROVENANCE.md"
  "blueprints/research/SNE-000D-BUILD-FAILURE-TAXONOMY.md"
  "blueprints/research/SNE-000D-BUILD-LANE-MATRIX.md"
  "blueprints/research/SNE-000D-CMAKE-OPTIONS.md"
  "blueprints/research/SNE-000D-COMPILER-TOOLCHAIN.md"
  "blueprints/research/SNE-000D-DEPENDENCY-LOCK-PROTOCOL.md"
  "blueprints/research/SNE-000D-HARDWARE-CAPTURE.md"
  "blueprints/research/SNE-000D-MEASUREMENT-SOP.md"
  "blueprints/research/SNE-000D-OPEN-QUESTIONS.md"
  "blueprints/research/SNE-000D-PERFORMANCE-DECISION-GATES.md"
  "blueprints/research/SNE-000D-REPRO-BUILD-COMMANDS.md"
  "blueprints/research/SNE-000D-TEST-SCENES.md"
  "blueprints/research/SNE-000D-THREAT-LICENSE-CHECKLIST.md"
  "blueprints/research/SNE-000D-WINDOWS-ENV-INVENTORY.md"
  "docs/WO-000D-START-HERE.md"
  "evidence/sources/SNE-000D-PIN-LEDGER.md"
  "evidence/sources/SNE-SRC-BIASEDDOOM-004.md"
  "evidence/sources/SNE-SRC-GZDOOM-004.md"
  "evidence/sources/SNE-SRC-UZDOOM-004.md"
  "evidence/sources/SOURCE-INDEX.md"
  "governance/WO-000D-REVIEW-FINDINGS.md"
  "governance/WO-000D-RISK-REGISTER.md"
  "registry/PHASE-00-ARTIFACT-INDEX.md"
  "scaffold/WO-000D-BUILD-VERIFICATION.json"
  "scaffold/WO-000D-CHANGELOG.md"
  "scaffold/WO-000D-FILE-SHA256.json"
  "scaffold/WO-000D-MANIFEST.md"
  "templates/SNE-000D-BUILD-RECORD.json"
  "templates/SNE-000D-DEPENDENCY-RECORD.json"
  "templates/SNE-000D-HARDWARE-RECORD.json"
  "templates/SNE-000D-README.md"
  "templates/SNE-000D-REVIEW-RECORD.json"
  "templates/SNE-000D-RUN-RECORD.json"
)
git add -- $wo000dPaths
```

## Staged verification

```powershell
git diff --cached --check
git diff --cached --stat
git status --short
```

Expected staged file count: **45**, whitespace errors **0**, modifications 7, additions 38. This staged check includes new files ignored by the initial unstaged check. Compare `scaffold/WO-000D-FILE-SHA256.json` and `scaffold/WO-000D-BUILD-VERIFICATION.json` before recording the package as ready.

## Operator-controlled commit/push (only after review)

```powershell
git commit -m "docs: document SNE-WO-000D Windows build and UHD 620 test protocol"
git push origin main
```

No engine test, dependency installation, fork modification, compiled binary or game launch is authorized by these Git steps. If any staged check fails, do not commit; reconcile the exact files. Report successful commit hash and push output for WO-000E checkpoint.
