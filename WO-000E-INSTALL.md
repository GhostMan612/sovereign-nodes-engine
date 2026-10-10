# SNE-WO-000E v0.7.0 — Safe local installation

**Destination:** extract archive into `C:\`, NOT into `C:\sovereign-nodes-engine` (otherwise double nesting).
**Expected HEAD:** `1f21e4c99da50c83ac0c90d14b2f14a752ae89f4`. Changes: **8 REPLACE + 40 ADD = 48 files**.

## 0. STOP if source differs

Run from PowerShell:

```powershell
cd C:\sovereign-nodes-engine
git rev-parse HEAD
git status --short
```

Expect exact HEAD above and **no status output**. Stop for dirty work, different branch, existing ADD paths or previous extracted files; do not stash/reset or overwrite without reconciliation.

## 1. Optional but recommended preimage check

Run each replacement's `git rev-parse HEAD:<path>` and compare SHA-1 to the corresponding row in `scaffold/WO-000E-MANIFEST.md` inside the ZIP before extracting. A normal Windows ZIP extractor does not enforce these guards.

## 2. Extract once into C:\

Inspect archive root `sovereign-nodes-engine/`, then extract into `C:\` and allow the **eight documented replacements** only. Do not extract into your existing repo's own folder.

## 3. Inspect before staging

```powershell
cd C:\sovereign-nodes-engine
git status --short
git diff --check
git diff --stat
```

Expect exactly 8 modified files and 40 additions, sometimes represented as grouped `??` directories; LF/CRLF notes may appear and are not whitespace errors. Review changes; the unstaged check cannot see new untracked file whitespace.

## 4. Stage by all explicit paths

```powershell
git add -- `
  WO-000E-INSTALL.md `
  artifact-chain/acceptance/SNE-ACC-000E.md `
  artifact-chain/evidence/SNE-EVD-000E.md `
  artifact-chain/reconciliation/SNE-REC-000E.md `
  artifact-chain/verification/SNE-VER-000E.md `
  artifact-chain/work-orders/SNE-WO-000E.md `
  blueprints/architecture/SNE-000E-BOUNDARY-REVIEW.md `
  blueprints/architecture/SNE-000E-DECISION-FLOW.md `
  blueprints/decisions/ADR-SNE-002-FOUNDATION-PENDING.md `
  blueprints/diagrams/SNE-000E-GATE-DEPENDENCIES.md `
  blueprints/phases/PHASE-00-FOUNDATION.md `
  blueprints/research/CANDIDATE-MATRIX.md `
  blueprints/research/RESEARCH-QUEUE.md `
  blueprints/research/SNE-000E-ADAPTER-VS-FORK.md `
  blueprints/research/SNE-000E-ALTERNATIVES-ANALYSIS.md `
  blueprints/research/SNE-000E-CANDIDATE-TRADEOFFS.md `
  blueprints/research/SNE-000E-CLAIM-AUDIT.md `
  blueprints/research/SNE-000E-COST-AND-MAINTENANCE.md `
  blueprints/research/SNE-000E-EVIDENCE-GAP-MATRIX.md `
  blueprints/research/SNE-000E-EXPERIMENT-PRIORITY.md `
  blueprints/research/SNE-000E-FOUNDATION-SCORECARD.md `
  blueprints/research/SNE-000E-GAME-DEFECT-ISOLATION.md `
  blueprints/research/SNE-000E-LEGAL-POLICY-GATES.md `
  blueprints/research/SNE-000E-ROLLBACK-PLAN.md `
  blueprints/research/SNE-000E-SEAMLESSNESS-REALITY.md `
  blueprints/research/SNE-000E-SECURITY-BOUNDARIES.md `
  blueprints/research/SNE-000E-TOOLCHAIN-BLOCKERS.md `
  docs/WO-000E-START-HERE.md `
  evidence/sources/SNE-000E-FOUNDATION-PIN-LEDGER.md `
  evidence/sources/SOURCE-INDEX.md `
  governance/PHASE-00-REVIEW-GATES.md `
  governance/WO-000E-DECISION-CONDITIONS.md `
  governance/WO-000E-INDEPENDENT-REVIEW-PROTOCOL.md `
  governance/WO-000E-INDEPENDENT-REVIEW-READY.md `
  governance/WO-000E-RED-TEAM-FINDINGS.md `
  governance/WO-000E-REVIEWER-QUESTIONS.md `
  governance/WO-000E-RISK-REGISTER.md `
  registry/PHASE-00-ARTIFACT-INDEX.md `
  scaffold/WO-000E-BUILD-VERIFICATION.json `
  scaffold/WO-000E-CHANGELOG.md `
  scaffold/WO-000E-FILE-SHA256.json `
  scaffold/WO-000E-MANIFEST.md `
  scaffold/WO-000E-SOURCE-CONFIDENCE.md `
  templates/SNE-000E-ADR-VOTE.json `
  templates/SNE-000E-COMPAT-PROOF.json `
  templates/SNE-000E-GATE-STATE.json `
  templates/SNE-000E-README.md `
  templates/SNE-000E-REVIEW-RECORD.json
```

## 5. Verify staged inventory (must be 48 files)

```powershell
git diff --cached --check
git diff --cached --stat
git diff --cached --name-only
(git diff --cached --name-only | Measure-Object -Line).Lines
```

A passing first command prints nothing; the final count should be **48**. Stop if paths differ from manifest or anything unexpected is staged.

## 6. Manual Git publication only after review

```powershell
git commit -m "docs: prepare SNE-WO-000E conditional foundation decision review"
git push origin main
```

Do not commit a PASS engine decision. After push verify HEAD and clean tree. The package changes documentation only; formal research and runtime acceptance are separate.
