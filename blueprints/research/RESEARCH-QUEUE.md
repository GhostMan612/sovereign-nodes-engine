# SNE-P00 — Evidence queue (F-02 v1.1.0)

Updated after F-01 operator publication `725fded39c0d50139ab76182211e32375bc2764e`. No host inventory, original PK3 hash, fixture, game run, legal clearance or independent review has been supplied to the author. `SOURCE-OBSERVED` is not `PASS`.

| ID | Priority | Closure requirement | Lane | State |
|---|---|---|---|---|
| R00-01 | P0 | Independent source/commit/blob inspection, reviewer signed | F-00 / AUTH-R | PENDING |
| R00-02 | P0 | Original B0 PK3 and lawful external IWAD hashes + archive identity | F-02A / scoped AUTH-H | NOT CAPTURED |
| R00-03 | P0 | Full transitive code/brand/asset rights SBOM | F-06 / AUTH-S | NOT CLEARED |
| R00-04 | P0 | C-001..C-008 actual unchanged-game parity with negative controls | F-04 / AUTH-T | NOT RUN |
| R00-05 | P0 | UZDoom AI-assisted upstream PR restriction vs downstream rights | F-06 | SOURCE-ONLY; review pending |
| R00-06 | P1 | voxel/glTF conditional model actual runtime/fallback | F-05 / AUTH-T/P | NOT RUN |
| R00-07 | P0 | ≥3 real UHD 620 frame traces per target scene/profile | F-05 / AUTH-P | NOT RUN |
| R00-08 | P1 | MAP01→MAP03 exits, save/zone semantics actual outcomes | F-04 / AUTH-T | NOT RUN |
| R00-09 | P0 | Godot bool true/false, schema/stale/invalid synthetic cases | F-02B/F-04 AUTH-F/T | NOT RUN |
| R00-10 | P1 | fork updates/conflict/maintenance assessment | F-06 | NOT RUN |
| R00-11 | P1 | WO-A checksum issues independently reconciled | F-00 | PENDING |
| R00-12 | P1 | BiasedDoom glTF ON/Python OFF build and model tests | F-03/F-05 AUTH-B/T | NOT RUN |
| R00-13 | P0 | Windows/MSVC/SDK/CMake tool inventory | F-02A / AUTH-H | NOT RUN |
| R00-14 | P0 | ORESHAA0/TOOLAA0/GLDEFS actual frame and actor binding | F-02B/F-04 AUTH-F/T | SOURCE HYPOTHESIS |
| R00-15 | P0 | `hasParadox` boolean vs `ScanInt` actual ToInt | F-02B/F-04 AUTH-F/T | SOURCE HYPOTHESIS |
| R00-16 | P1 | 0/2/8/16 light sweep and postFX thermal fallback | F-05 / AUTH-P | NOT RUN |
| R00-17 | P1 | ZDaemon dedicated native multiplayer compatibility | separate order | NOT RUN |
| R00-18 | P0 | immutable dependencies, game/engine resource and binary hashes | F-02/F-03 | MISSING |
| R00-19 | P0 | distinct reviewer F-00 / G7 dissent and acceptance | F-00 / AUTH-R | PENDING |
| R00-20 | P0 | foundation selection, accepted risks and rollback | F-07 / operator | HOLD |
| R00-21 | P0 | genuine signed per-category operator authorization and scope digest | F-01 controls | **NOT APPROVED** |
| R00-22 | P0 | `validate_pk3.py` historical path discrepancy vs actual packager functions | F-02/source review | OPEN |
| R00-23 | P0 | original PK3, real GapNode project geometry/actor, no-PK3 negative control | F-02/F-04 | NOT RUN |
| R00-24 | P0 | controlled B0 unchanged versus B1/B2 one-variable fixture isolation | F-02B / AUTH-F | NOT RUN |
| R00-25 | P1 | raw frame trace QA/scene equivalence | F-05 | NOT RUN |
| R00-26 | P0 | each C-series result reviewed and reconciled to gates | F-07 | NO RESULTS |
| R00-27 | P0 | permissions scoped to exact paths, time, actor and revocation | F-01 | TEMPLATE ONLY |
| R00-28 | P0 | F-00 claim corrections / independent counterchecks | F-00 | NOT COMPLETED |
| **R00-29** | P0 | correct original `build_pk3.py` intentional **SNDINFO exclusion** in future inventory oracle | F-02A | SOURCE-OBSERVED; STATIC NOT RUN |
| **R00-30** | P0 | original B0 raw SHA and WAD per-map checksums before any fixture/game result | F-02A | NOT CAPTURED |
| **R00-31** | P0 | actual AUTH-H inventory of host (no install) and signed provenance | F-02A | BLOCKED (no approval) |
| **R00-32** | P0 | B1 sprite and B2 bool fixture creation in off-repo approved path | F-02B | BLOCKED (no approval) |

**Next condition is genuine operator authorization**, not an automatic successor script; P00 G1–G8 remain OPEN.
