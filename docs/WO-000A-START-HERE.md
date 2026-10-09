# SNE-WO-000A — Reviewer packet

**Package:** SNE-WO-000A-RESEARCH-0003
**Research date:** 2026-10-09
**Target:** Sovereign Nodes Engine hybrid project
**Work-order scope:** existing-game source and compatibility inventory (000A); seed-level upstream reconnaissance for 000B.

## Main findings

1. Current game is **two separate runtimes**: a Godot 4 hub and an external ZDoom/GZDoom `.pk3`. It is **not** safe to merge their scripting or launch processes by assumption.
2. `MAPINFO.txt` names `MAP01 GapNode → MAP02 Breach → MAP03 Warren`, references three ZScript fragments and declares grammar `version "4.14"`.
3. `GLDEFS.txt` contains pointlights for `ELECA0`, `ORESHAA0`, `TOOLAA0` plus global fog; source declaration is not runtime lighting proof.
4. Godot `FpsLauncher.write_handoff()` writes JSON to both `user://` and the OS temp path, while Doom `SOVovereignHandoff.Read()` reads from OS temp. Both name schema 1; runtime compatibility and tamper resistance remain **NOT RUN / UNVERIFIED**.
5. `build_pk3.py` includes checks for fragment paths, schema keys, frames and map targets. These checks are source-observed; nobody ran them during this research.
6. GZDoom source already contains a voxel model loader/render pathway; BiasedDoom adds a source-visible glTF/fastgltf loader. Reuse before replacement.
7. UZDoom upstream rejects AI-assisted pull requests under its contribution policy. This policy is separate from GPL-based rights to independently modify a fork.
8. Original Doom and Chocolate Doom offer a useful source-reference lane but are not practical drop-in replacements for current ZScript-heavy game behavior.

## What we did **not** prove

- No local checkout or CMake configure/build; no game launch or map walkthrough; no full binary WAD inspection; no UHD 620 performance measurement; no acceptance approval; no per-dependency complete license audit.
- The available files were fetched and inspected through GitHub's repository reader at the full commit IDs in `evidence/sources/SNE-REVISION-LEDGER.md`. Only inspected files are represented as checked.
- We do not assert ZDaemon support for all advanced GZDoom features.

## Handoff

Continue read-only 000A review on the remaining gameplay and binary map invariants, then proceed with `SNE-WO-000B` deeper upstream source mapping and dependency-license verification. Do not choose a foundation until the operator accepts the final ADR.
