# IF-SNE-003 — Logical world continuity contract (DRAFT v0.5.0)

**Scope:** game-safe independent conceptual model. **No physical seamless-streamed map feature exists or is proven.** Inherited GZDoom/UZDoom `g_level.cpp` and `g_hub.cpp` demonstrate level/snapshot infrastructure, not a multi-map live engine.

## Logical data model (proposal, not a serialized implementation)

| Field | Concept | Validation |
|---|---|---|
| `ZoneId` | namespace-scoped stable logical identifier | fixed normalized naming, not raw external paths |
| `MapId` | Doom map lump name | must resolve against packaged map registry |
| `PortalLink` | source, target, exit and spawn binding | no dangling destination; ownership checked |
| `TransitionSnapshot` | explicit bounded state subset | schema/version, deterministic mapping and integrity |
| `ZoneRegistry` | zone-to-map/source metadata | static validated list; no direct Mantle queries |
| `RunId` | synthetic session correlation token | cannot authorize personal-data access |

## Four independent stages

1. **Stage W1: conventional map exits** — MAP01→MAP02→MAP03 and explicit persistence checks. No new renderer.
2. **Stage W2: logically persistent world** — save/import a versioned, bounded player/mission snapshot at transitions, define re-entry, visits and conflicts. No concurrent geometry.
3. **Stage W3: perceptual continuity** — optional prefetch, transition UI/cut timing, fade/portal presentation; engine still changes active maps sequentially.
4. **Stage W4: physical continuous zones** — simultaneous active cell state, collision, visibility, render-through portals, audio, AI and save authority. Requires a separate engine-architecture ADR and extensive proof; not a near-term compatibility promise.

## Failure containment

No shared arbitrary filename payload, no real genealogy identifiers, no asset-dependent gameplay state written to Mantle. On failed load: stop transition with recoverable error, preserve last valid snapshot, do not invent a destination. Record backward compatibility and rollback gate before implementation.

## Candidate seams and evidence

GZDoom/UZDoom `src/g_level.cpp` and `src/g_hub.cpp` contain relevant existing level/hub machinery (pinned in WO-C source records). Maplink handling test C-003, persistence test C-009, world-state test W-001 to W-004 remain NOT RUN.
