# SNE-REC-F01 — Overlay integration and historical state reconciliation

- Overlay preimage: `148dc28cdbdf4970c8011d76762b31b8dcafea0b`. Git SHA is **parent** only; resulting F-01 commit unknown until operator creates and pushes it.
- F-00 publishing: `148dc28` verified; original v0.9.0 packet's "prepared" phrasing remains historical truth at its authoring point, not silently edited.
- Existing WO-000F earlier preimage and prior original game pins are preserved; no direct edits to historical F-00 review records or foundation ADR.
- This overlay updates only five listed evolving Phase-00 governance/queue/index docs and adds a new F-01 track. Full replacement path list, baseline SHA-1 and SHA-256 ledger in `scaffold/SNE-F01-MANIFEST.md`.

## Post-extraction operator reconciler

1. Confirm clean exact HEAD `148dc28cdbdf4970c8011d76762b31b8dcafea0b` **before** extracting; if files already modified or an ADD exists, STOP and inspect before any overwrites.
2. Extract ZIP to `C:\`, not `C:\sovereign-nodes-engine`, to avoid double nesting.
3. Check `git status --short`, `git diff --check`; stage exactly the file list in `SNE-F01-INSTALL.md` (never `git add .`).
4. Check staged `git diff --cached --check`, file count, 5 modified+37 added and full diff. Verify no unexpected files, deletions or game/engine edits.
5. Operator alone decides commit/push; actual resulting SHA belongs to future register update, not prefilled here.

No consent status, G1–G8 state, independent reviewer signature or engine decision is advanced by Git reconciliation.
