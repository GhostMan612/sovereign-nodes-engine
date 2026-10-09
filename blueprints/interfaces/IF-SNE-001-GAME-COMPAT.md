# IF-SNE-001 — Doom gameplay and packaged-resource contract (DRAFT v0.5.0)

## Ownership and immutability

`GhostMan612/Sovereign-Nodes/games/SovereignNodesFPS` owns the existing FPS. `C:\sovereign-nodes-engine` contains only research and future separately authorized engine work. No game script, map, resource, or generator is overwritten in WO-000C.

## Inputs and baseline

- Legitimately sourced IWAD external to Git; same hash/rights across comparisons.
- Canonical Doom PK3 generated from `games/SovereignNodesFPS/{game,zscript,maps,sprites}` by its own build tooling.
- `MAPINFO.txt`: first directive `version "4.14"`; `addfragments` references `zscript/core.zs`, `sn_handoff.zs`, `hud.zs`.
- `GLDEFS.txt`: ELEC, ORESHA, TOOLA light definitions with explicit texture/frame bindings.
- `zscript/doomednum.txt`: custom thing IDs and class Tags; map slots and spawn points validated by owner tooling.
- `MAP01` GapNode → `MAP02` Breach → `MAP03` Warren; third map has no assumed follow-on target.

## Required observable outputs

1. The active map is identified as **custom GapNode**, not Doom II Entryway, using both display name and unique custom object interaction.
2. Custom actors, inventory, weapon, altar, HUD and handoff classes compile/load without silent omission.
3. Exact sprite identity at runtime is checked; mere file existence does not prove actor frame resolution.
4. Light definitions are actually attached and visible; parser success alone is insufficient.
5. Inventory and health/collision/damage semantics are invariant when substituting voxels/models.
6. Map progression and save/load preserve only explicitly specified mission/player state, with comparison recorded.
7. The optional hub handoff does not break standalone FPS when absent.

## Blocking unknowns

- `ORESHAA0`/`TOOLAA0` appear inconsistent with GZDoom four-character sprite-prefix + frame/rotation decoding; treat as suspected issue pending runtime.
- Godot bool `hasParadox` vs ZScript `ScanInt` may not round-trip.
- Unknown/newer schema currently tolerated by reader; no authoritative rejection guarantee.
- ZDaemon may not support GZDoom ZScript/GLDEFS semantics: a distinct test target, not a transparent replacement.

## Verification

C-001…C-009, C-011, C-015 plus catalog test subcases. No implied universal GZDoom-mod compatibility; no invisible fallback to IWAD maps.
