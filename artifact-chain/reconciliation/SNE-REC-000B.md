# SNE-REC-000B — Overlay reconciliation record

**Status:** PREPARED, awaiting operator extraction + Git commit evidence.

## Expected

- Version v0.4.0; root `sovereign-nodes-engine/` inside ZIP.
- No source files or engine forks.
- Every replacement is listed in the manifest with expected old Git blob SHA.
- New files are additive; existing colliding paths are conflicts, never silently overwritten without review.
- Historical WO-000A ZIP-byte SHA manifest remains untouched; separate committed normalization ledger records the whitespace corrections.

## After installation

Record repository HEAD, local diff, `git diff --check`, staged file count, SHA manifest validation, Git commit, origin push and resulting SHA. Report changes not described in the manifest as a block.

## End state

SNE-WO-000B becomes published research material only after clean commit/push; technical acceptance still requires independent source review. Phase 00 and engine selection remain open.
