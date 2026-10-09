# SRC-GAME-001 — Sovereign Nodes source ledger

**Repo:** `GhostMan612/Sovereign-Nodes`
**Revision:** `44034e97fd22129f919a18cadceb84466ef1bcd3`
**Classification:** SOURCE-OBSERVED / EXECUTION-NOT-RUN
**Reader:** ChatGPT architecture review; independent review outstanding.

## Direct file observations

- [`README.md`](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/README.md) — Defines Godot 4 hub and separate standalone Doom engine FPS; shared canon is read-only at runtime.
- [`RULES.md`](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/RULES.md) — Operator laws: no secrets/IWADs; explicit staging paths; ZDoom and Godot boundaries; synthetic data only.
- [`games/SovereignNodesFPS/game/MAPINFO.txt`](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/game/MAPINFO.txt) — First directive version 4.14; three fragments; MAP01 → MAP02 → MAP03; clusters 1–3.
- [`games/SovereignNodesFPS/game/GLDEFS.txt`](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/game/GLDEFS.txt) — ELEC/ ORESHA/ TOOLA pointlight and frame bindings plus globalfog.
- [`games/SovereignNodesFPS/zscript/core.zs`](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/zscript/core.zs) — SNConst frame identifiers and custom actor/inventory logic.
- [`games/SovereignNodesFPS/zscript/hud.zs`](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/zscript/hud.zs) — SNStatusBar renders ore, locators, scoreboard, and handoff state.
- [`games/SovereignNodesFPS/zscript/sn_handoff.zs`](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/zscript/sn_handoff.zs) — SOVovereignHandoff reader, schema version 1, temp path and scalar extraction.
- [`games/SovereignNodesFPS/zscript/doomednum.txt`](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/zscript/doomednum.txt) — Maps game actor classes to 9033–9036 and 9040–9041.
- [`games/SovereignNodes/src/world/fps_launcher.gd`](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodes/src/world/fps_launcher.gd) — FpsLauncher discovers external executable/IWAD/PK3 and creates handoff before launching.
- [`games/SovereignNodesFPS/tools/build_pk3.py`](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/tools/build_pk3.py) — Checks fragment inclusion, contract shape, referenced assets and map targets before package writing.
- [`games/SovereignNodesFPS/tools/build_maps.py`](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/tools/build_maps.py) — Room/edge map generator and custom WAD writing constraints.
- [`games/SovereignNodesFPS/tools/validate_wads.py`](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/tools/validate_wads.py) — Project-specific WAD byte and semantic validation; not yet executed.

## Tier-A identity invariants

- The actual packaged PK3 must contain custom `MAP01`, `MAP02`, `MAP03` and all three ZScript fragments; log messages alone do not prove this.
- Exact model/asset frame names: `ELECA0`, `ORESHAA0`, `TOOLAA0`. Their presence in game source doesn't prove the shipped PK3 contains them.
- The existing hub must be able to locate an external engine binary and the operator-provided, legally obtained IWAD without hardcoded locations.
- Handoff schema constant exists in BOTH producers (`HANDOFF_SCHEMA := 1` in `fps_launcher.gd`) and consumer (`HANDOFF_SCHEMA_VERSION = 1` in `sn_handoff.zs`); fields include run ID, seed, node ID, ancestor ID/name, relationship, paradox and integrity.
- HUD must visibly display custom gameplay counters and handoff data, not vanilla Doom counters alone.
- Runtime/ZDaemon compatibility is **not inferred** from file comments.

## Clarifications and known risk

- `validate_wads.py` requires `dirofs == 12` for the **project's generated WAD layout**. This is a project rule; it is NOT a universal requirement of the Doom WAD format, whose directory offset is stored in the header.
- Current reader accepts some unknown/unstamped or newer-schema data as unverified according to its source; this is a compatibility choice, not tamper-proof validation. A future Mantle Bridge MUST be stricter, with sanitized snapshots and content limits.
- Game-side parser loops over an unbounded file until EOF according to source; review resource caps before accepting untrusted input.
- Existing `SESSION_HANDOFF.md` contains historically reported fixed defects; do not convert historical claims into current tests.

## Not inspected

The bytes of three `.wad` binaries, complete generated PK3, third-party IWAD, complete scripting call graph, and game runtime output. Additional enumeration and an operator-led playtest remain needed to close all 000A gates.
