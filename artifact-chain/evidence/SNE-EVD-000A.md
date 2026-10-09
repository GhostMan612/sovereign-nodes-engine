# SNE-EVD-000A — Evidence receipt

**Type:** CURATED READ-ONLY SOURCE REVIEW
**Captured:** 2026-10-09
**Source pins:** `evidence/sources/SNE-REVISION-LEDGER.md`
**Test state:** ALL BUILD / RUNTIME / BENCHMARK CASES NOT RUN.

## Proven from source text

1. Game split (Godot hub / Doom FPS): README + AGENTS + launcher.
2. MAP01/02/03 flow and ZScript fragments: MAPINFO.
3. GLDEFS light definitions and binding frames: GLDEFS.
4. Schema v1 JSON producer in Godot and reader in ZScript, OS temp path selection and HUD consumer.
5. Build-time check code for fragments, source/sink keys, sprite frames, map constraints.
6. GZDoom voxel implementation files, UZDoom scripting/build features and contributions policy, BiasedDoom glTF feature-gated implementation, classic Doom reference.

## Evidence pointers

- Game: `evidence/sources/SNE-SRC-GAME-001.md`
- GZDoom: `evidence/sources/SNE-SRC-GZDOOM-001.md`
- UZDoom: `evidence/sources/SNE-SRC-UZDOOM-001.md`
- BiasedDoom: `evidence/sources/SNE-SRC-BIASEDDOOM-001.md`
- Classic: `evidence/sources/SNE-SRC-CLASSIC-001.md`

## Limits

This is not a line-by-line engine audit; some files were read only as excerpts. No source compilation, assets unpacking, binaries, graphics tests or hardware benchmarks were performed. Reviewed SHA means source snapshot, not a verified release build. Reviewer acceptance outstanding.
