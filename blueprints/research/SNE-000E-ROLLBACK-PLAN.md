# WO-E — Rollback and foundation exit strategy

## During research

The ZIP only changes documentation in `C:\sovereign-nodes-engine` after operator extraction. If baseline/checksum mismatch, STOP; do not overwrite. If committed documentation must be reverted, use an operator-reviewed ordinary Git revert or prior commit after inspecting all affected files; no destructive reset or force push.

## In a future authorized fork trial

- Keep pristine upstream commit/tag and its source tar/checksum; keep source game and licensed IWAD separate.
- Change fork/extension module behind feature flags; never treat experimental renderer, Python, model importer or Mantle data bridge as mandatory P0.
- Preserve a launchable stock P0 graphics/content pathway and independent custom MAP01, ZScript/HUD/handoff smoke tests.
- Record minimal patch manifest and versioned saved-game compatibility boundary; do not promise cross-fork savegame interoperability.
- If P1–P3 visual upgrade regresses physics, save/restore, crashes or UHD 620 p99, disable the feature and return to last verified P0 baseline.
- If a fundamental engine source fork fails G2/G3/G4/G5/G6 or becomes unmaintainable, return to alternative comparator; no sunk-cost automatic endorsement.

## Roll-forward blockers

Any new upstream release must renew source pins, license/security review and compatibility tests; a previously accepted build does not certify later binary. Private Mantle data never follows game rollback artifacts or crash dumps.
