# F-00 v0.9.0 — Safe local overwrite installation

**ZIP root:** `sovereign-nodes-engine/`.
**Extraction location:** `C:\` only (not `C:\sovereign-nodes-engine`, to avoid nested repo folders).
**Exact required clean HEAD:** `1c01d2ff5bc3a1369210a7d68dd58269ecf6506d` on `main`.
**Actions:** 6 REPLACE + 39 ADD = **45** Markdown/JSON files. No deletes, executable files, engine code, source games, WAD/IWADs, `.git`, installers, private data or agent chat logs.

## Before extracting anything: stop conditions

1. Confirm `git rev-parse HEAD` is exactly `1c01d2ff5bc3a1369210a7d68dd58269ecf6506d`. **STOP** if it is not.
2. Confirm `git status --short` is blank and no staged or untracked work will be overwritten. **STOP** if dirty.
3. Verify all six REPLACE preimage Git blob IDs against `scaffold/SNE-F00-MANIFEST.md`; verify no intended ADD already exists. **STOP** on mismatch.
4. Archive extraction itself cannot enforce these guards. The operator checks them manually; no file is installed automatically by this Markdown.

Suggested read-only PowerShell precheck:

```powershell
cd C:\sovereign-nodes-engine
git status --short
git rev-parse HEAD
```

Read `scaffold/SNE-F00-MANIFEST.md` for every intentional path and expected Git blob. You may also verify each existing tracked file with `git rev-parse 'HEAD:repo/relative/path'` (no mutation); an untracked ADD path must not already exist locally.

## Extract and inspect

After all guards pass, extract this ZIP to **`C:\`**. The archive contains its own `sovereign-nodes-engine` directory and merges into your local checkout.

```powershell
cd C:\sovereign-nodes-engine
git status --short
git diff --check
git diff --stat
```

You should see six modified paths and 39 additions (new files may be grouped under untracked directory headings). `git diff --check` before staging does not examine the untracked files; the staging check below includes them. LF→CRLF warnings on Windows are informational, not automatically errors.

## Stage only the exact 45 package files

```powershell
git add -- `
  SNE-F00-INSTALL.md `
  artifact-chain/acceptance/SNE-ACC-F00.md `
  artifact-chain/evidence/SNE-EVD-F00.md `
  artifact-chain/reconciliation/SNE-REC-F00.md `
  artifact-chain/verification/SNE-VER-F00.md `
  artifact-chain/work-orders/SNE-WO-F00.md `
  blueprints/architecture/SNE-F00-AUDIT-BOUNDARY.md `
  blueprints/diagrams/SNE-F00-REVIEW-FLOW.md `
  blueprints/phases/PHASE-00-FOUNDATION.md `
  blueprints/research/RESEARCH-QUEUE.md `
  blueprints/verification/SNE-000F-RESULT-REGISTER.md `
  blueprints/verification/SNE-F00-BUILD-CLAIMS-REVIEW.md `
  blueprints/verification/SNE-F00-CANDIDATE-POLICY-REVIEW.md `
  blueprints/verification/SNE-F00-CLAIM-CATALOG.md `
  blueprints/verification/SNE-F00-DISSENT-RESOLUTION.md `
  blueprints/verification/SNE-F00-EVIDENCE-CHAIN.md `
  blueprints/verification/SNE-F00-GATE-IMPACT.md `
  blueprints/verification/SNE-F00-HANDOFF-PARSER-REVIEW.md `
  blueprints/verification/SNE-F00-NEXT-WORKORDER-ENTRY.md `
  blueprints/verification/SNE-F00-PIN-AND-BLOB-CHECKS.md `
  blueprints/verification/SNE-F00-PK3-VALIDATOR-REVIEW.md `
  blueprints/verification/SNE-F00-REVIEW-INTAKE.md `
  blueprints/verification/SNE-F00-REVIEWER-CHECKLIST.md `
  blueprints/verification/SNE-F00-SOURCE-SAMPLING.md `
  blueprints/verification/SNE-F00-SPRITE-PARSER-REVIEW.md `
  docs/SNE-F00-START-HERE.md `
  evidence/sources/SNE-F00-ENGINE-PRIMARY-OBSERVATIONS.md `
  evidence/sources/SNE-F00-GAME-PRIMARY-OBSERVATIONS.md `
  evidence/sources/SNE-F00-PIN-LEDGER.md `
  evidence/sources/SOURCE-INDEX.md `
  governance/PHASE-00-REVIEW-GATES.md `
  governance/SNE-F00-AUTHOR-FINDINGS.md `
  governance/SNE-F00-CONFLICT-OF-INTEREST.md `
  governance/SNE-F00-REVIEW-ASSIGNMENT.md `
  governance/SNE-F00-RISK-REGISTER.md `
  registry/PHASE-00-ARTIFACT-INDEX.md `
  scaffold/SNE-F00-BUILD-VERIFICATION.json `
  scaffold/SNE-F00-CHANGELOG.md `
  scaffold/SNE-F00-MANIFEST.md `
  scaffold/SNE-F00-SHA256.json `
  templates/SNE-F00-CLAIM-REVIEW.json `
  templates/SNE-F00-INDEPENDENT-REVIEW.json `
  templates/SNE-F00-ISSUE-RECORD.json `
  templates/SNE-F00-OPERATOR-DECISION.json `
  templates/SNE-F00-README.md
```

## Full staged verification

```powershell
git diff --cached --check
git diff --cached --stat
git diff --cached --name-only
git diff --cached --name-only | Measure-Object -Line
git status --short
```

Expected count 45; first check should print no whitespace errors. Inspect complete staged diff and verify additions/replacements, not just the summary. The hash ledger `scaffold/SNE-F00-SHA256.json` authenticates the ZIP members except itself, not your independently edited local files after extraction. If any unexpected modification appears, **STOP** and reconcile explicitly; do not mass-reset or mass-stage.

## Operator-only commit/push (after staged review)

```powershell
git commit -m "docs: prepare SNE-F00 independent source review handoff"
git push origin main
```

Do **not** run the commit or push until staged inspection passes. Capture the new SHA afterward and update publication status only in a later **new** reconciliation artifact. Git publication proves docs were pushed, not independent G7 review, engine compatibility, UHD performance, rights clearance, or foundation decision.

## Recovery

Wrong HEAD, dirty tree, preimage mismatch, existing ADD, corrupt ZIP, missing expected path, privacy issue, or accidental unapproved authorization ⇒ STOP before overwriting. Use local copies and manual diff reconciliation. Never use `git reset --hard`, `git clean`, force push, `git add .`, or mutate source game/engine repos to solve an overlay conflict.
