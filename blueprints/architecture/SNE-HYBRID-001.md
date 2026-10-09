# SNE-HYBRID-001 — Hybrid architecture

- Status: PROPOSED / UNVERIFIED
- Goal: preserve Doom/WAD/PK3/ZScript compatibility where proven; extend renderer, voxel actors, world continuity and optional Mantle bridge.
- Foundation: undecided pending Phase 00 source and license audit.

## Architectural principles
1. Existing Sovereign Nodes FPS is the Tier-A regression target.
2. Keep inherited game simulation/actor semantics until evidence warrants change.
3. Introduce new capabilities behind explicit interfaces; do not rewrite upstream renderer preemptively.
4. Start with voxel **models**, not editable voxel terrain.
5. Logical cross-map persistence precedes physically seamless streamed worlds.
6. Mantle data flows through allowlisted, signed, redacted, versioned **read-only** exports; synthetic data first.
7. Intel UHD 620 is the initial performance baseline; test rather than assume.

## Logical modules
`compatibility`, `rendering`, `voxels`, `world`, `gameplay`, `assets`, `scripting`, `integrations/mantle`, `platform`.
These are **logical modules**, not permission to rearrange upstream source.

## Compatibility tiers
A: project maps and scripts; B: common Doom-family content; C: arbitrary mods and historical saves (best effort).

## Unresolved decisions
- GZDoom vs UZDoom vs another source foundation
- GPU renderer/backend and supported versions
- glTF and voxel asset import route
- Cross-map persistence implementation
- License obligations and bundled dependencies
- Testable performance budgets

## Phase gates
See `blueprints/phases/` and `artifact-chain/README.md`.
