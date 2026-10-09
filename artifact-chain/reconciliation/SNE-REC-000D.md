# SNE-REC-000D — Overlay reconciliation checkpoint

- Intended base: `706db57a4fbabd701244dd9e4674a59f7ab044f3`
- Archive root: `sovereign-nodes-engine/`; extract only to `C:\` when clean and exact baseline.
- Additions and replacements: see generated `scaffold/WO-000D-MANIFEST.md` and SHA-256 ledger.
- Local extraction: NOT OBSERVED by author.
- Post-extraction `git status --short`: NOT OBSERVED.
- Staged `git diff --cached --check`: NOT OBSERVED.
- Git commit and origin push: PENDING operator.

## Reconciliation procedure

Check HEAD and clean tree before merging ZIP; verify added paths do not collide, inspect every replaced file diff; stage only explicit paths. After staged check, capture new commit SHA; update the registry in the **next** package instead of retroactively claiming this ZIP was committed before publication.

## Rollback

If the pre-extraction tree was clean and operator has not staged unrelated work, inspect the overlay diff and restore only its known REPLACE files from the baseline while removing only its known ADD files after deliberate review. No destructive cleanup or wildcard deletes. Never run force reset to recover from an overlay.
