# WO-F — Exhaustive C-series to gate, owner and evidence map

All cases **NOT RUN**; results have not been assigned. Use `templates/SNE-000F-CASE-RESULT.json` per engine/scenario/fixture. For every test, unchanged original game proof precedes mutation/control. `G3` covers C-001…C-008; high cases and G6/G5 may independently block a candidate.

| Case | Test objective and required oracle | Gate | Future owner | Blocking precondition |
|---|---|---|---|---|
| C-001 | actual unique custom GapNode + project actor vs no-PK3 Entryway negative | G3 | game tester | legal IWAD, identical PK3 |
| C-002 | MAPINFO 4.14, exactly three `addfragments`, real classes/HUD | G3 | game tester | C-001 correct |
| C-003 | MAP01→MAP02→MAP03 exits and map IDs | G3 | game tester | C-001/02 |
| C-004 | correct ore/locator/altar/weapon, DoomEdNum and sprite frames | G3 | game tester | sprite family source risk isolated |
| C-005 | GLDEFS actor-bound lights visually change scene vs off/omitted association | G3 | graphics tester | C-004 actor frames |
| C-006 | Godot→Doom synthetic handoff seed/runId/name; true/false | G3/G6 | handoff tester | synthetic producer and path permission |
| C-007 | HUD counters before/after pickup and standalone no-handoff case | G3 | gameplay tester | C-002/04/06 |
| C-008 | generated WAD bytes, starts, exits and *actual* custom gameplay | G3 | game validator | validate true on-disk tool location |
| C-009 | save/load across map transitions and zone state | G3/G6 | gameplay tester | C-001…08 baseline |
| C-010 | real OpenGL/Vulkan backend or explicit fallback | G5 | renderer tester | host driver inventory |
| C-011 | voxel then separately glTF/GLB model, actor behavior invariant | G3/G5 | rendering tester | P0 stable; feature flags |
| C-012 | 0/2/8/16 visible lights, frame times p50/p95/p99 | G5 | device operator | no VSync/scene confounds |
| C-013 | lawful curated third-party test set | G2/G3 | rights/game reviewer | asset rights |
| C-014 | ZDaemon native compatibility, not GZ parity assumption | separate | multiplayer tester | separately pinned ZDaemon |
| C-015 | missing/stale/malformed/schema/boolean handoff rejects safely | G6 | security tester | no private Mantle data |

## Required negative control counts

- C-001 missing PK3; C-002 missing fragment; C-004 wrong sprite; C-005 GLDEFS binding omitted; C-006 true/false numeric comparison; C-008 malformed project-map copy; C-012 lights-off control; C-015 stale/unknown-schema/corrupt file.
- Controls must be in **disposable** fixtures, not source-game modifications, and each receives a unique hash, case and execution record.
- Each official candidate uses its own actual engine binary SHA, source SHA and renderer ID. Passing a scenario on GZDoom does not certify UZDoom, BiasedDoom or ZDaemon.

## Gate aggregation

G3 requires all mandatory C-001…C-008 case results `PASS` for the candidate on **unchanged** original PK3, without incomplete negative controls or contradictory logs. A fixture that fixes a baseline error opens a new repair work order; it does not automatically close G3. G5 additionally requires three device runs per target scenario. G6 remains open until risky handoff input and Python boundary have been independently reviewed. G8 never aggregates unchecked results.
