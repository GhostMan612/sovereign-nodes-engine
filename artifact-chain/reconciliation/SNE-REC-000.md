# SNE-REC-000 — Overlay reconciliation checklist

1. Record pre-extract Git HEAD and dirty paths.
2. Compare replacements against `scaffold/PHASE-00-MANIFEST.md`.
3. Do not overwrite customized replacements without operator inspection.
4. Extract top-level `sovereign-nodes-engine/` into `C:\`.
5. Inspect `git diff --check`, `git status --short`, changed paths and README/index links.
6. Log any changes to operator local files; record skipped overwrites and conflicts.
7. Commit documentation changes only on operator approval.
8. Preserve prior commit for rollback; never force-push or reset without operator direction.

Status: awaiting operator installation.
