# IF-SNE-001 — Existing Doom game compatibility interface (DRAFT)

## Owned by

Existing `GhostMan612/Sovereign-Nodes/games/SovereignNodesFPS`, not the SNE engine repo.

## Contract

- Input: legitimate Doom data resources, project's packaged PK3 and three WAD maps, custom ZScript fragments and map/light definitions.
- Parser contract: MAPINFO version and fragment loading as authored; fail visibly on missing custom content rather than falling back unnoticed to base IWAD.
- Simulation contract: inherited actor spawning, damage, inventory, HUD and level exits preserved before adding custom visual components.
- Output: expected map identity, actor states, transitions, logs and deterministic test markers.

## Forbidden shortcuts

No blanket promise of arbitrary GZDoom mod parity. No GLDEFS or ZScript assets silently ignored. No reimplementation of gameplay simulation when visual model replacement suffices.

## Verification

C-001…C-009. Exact implementation mappings and binary compatibility remain OPEN.
