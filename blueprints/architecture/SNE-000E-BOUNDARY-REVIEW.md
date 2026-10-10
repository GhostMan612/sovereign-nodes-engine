# WO-E — Architectural boundary review

## Runtime boundaries under test

1. **Existing game content** (`GhostMan612/Sovereign-Nodes/games/SovereignNodesFPS`): current ZScript, MAPINFO, GLDEFS, sprite assets, generated WADs. It is not automatically writable by an SNE engine feasibility study.
2. **Candidate engine runtime:** GZDoom/UZDoom, or BiasedDoom research variant. Inherited parser, actors, renderer, saves and map changes must be tested before patching.
3. **Presentation extensions:** VOXELDEF / model declaration, model loader and lighting controls should not alter simulation logic, collision, weapons, inventory or save semantics unless explicitly designed and tested.
4. **Godot station handoff:** separate producer and receiver, synthetic JSON only, version checks, path/size bounds and immutable run ID. Existing temp handoff is not authenticated; do not claim signatures already exist.
5. **Sovereign Mantle:** separate protected ledger/graph/vault. No direct read/write by a game renderer, model loader, Python mod or experimental fork. Future bridge uses explicit minimized opt-in export; separate threat model.

## Security and behavior invariants

- A missing, invalid or stale handoff produces an observable safe state; no private input reaches logs/screenshots or public Git.
- Actor presentation swap does not modify combat rules, item pickup, sound, collision, replication or authoritative inventory.
- Save/load and logical zone transitions preserve only explicitly enumerated state, not undefined 'seamlessness'.
- Every test observes **custom game identity** to avoid the silent stock IWAD fallback pitfall.
- Embedded CPython from BiasedDoom is unsandboxed and process-authority code; never call it a benign data plugin.

## Source review vs verification

WO-C and WO-D identify candidate seams and measurement protocols. No source-level assertion replaces tests of actual game behavior or device safety. An independent reviewer must confirm boundaries and attack assumptions before implementation authorization.

## Not authorized

Network/mod installation, engine forks, interprocess data integration, signed event ledger link, WAD redistribution and code edits are not authorized by this design review.
