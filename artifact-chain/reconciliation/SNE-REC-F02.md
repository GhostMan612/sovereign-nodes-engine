# SNE-REC-F02 — Baseline and operator reconciliation queue

- Required clean pre-extraction parent: `725fded39c0d50139ab76182211e32375bc2764e`.
- Known F-01 operator commit: `725fded39c0d50139ab76182211e32375bc2764e`; previously authored F-00 documents may still describe earlier state historically. This forward-looking registry corrects status without overwriting old signed/history files.
- Replaced files: exact paths and Git **blob SHA-1** listed in `scaffold/SNE-F02-MANIFEST.md`, to be matched before overlay.
- Added files: must not already exist; no `.git`, binaries, scripts, real genealogy, proprietary IWAD or game-source patches included.
- `SNDINFO` intentional omission: newly emphasized source finding; no actual PK3 audited.

## Operator post-install review

Verify `git diff --check`, `git status --short`, exact 45 paths after staging (the final quantity is manifest-defined), `git diff --cached --check` and inspect complete staged diff before local commit. On wrong parent or unexpected pre-existing file, stop; no forced cleanup or overwrite. Record the actual **future** commit SHA only once user has pushed.

Source state and independent signoff are not equivalent to archive integrity. `ADR-SNE-002` stays HOLD.
