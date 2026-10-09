# SNE-WO-000C — Compatibility matrix (test specification, not execution)

**Status:** Every runtime result **NOT RUN** at authoring. Source inspection only. Baseline pinned in `evidence/sources/SNE-000C-PIN-LEDGER.md`. The source game is not modified by this package.

| Case | Priority | Exact scenario | Observable pass evidence | Candidate lanes | Result |
|---|---|---|---|---|---|
| C-001 | BLOCKER | Correct PK3/custom MAP01, no IWAD Entryway fallback | custom MAP01 title/unique marker and engine load log | GZ/UZ/BD | NOT RUN |
| C-002 | BLOCKER | MAPINFO `version "4.14"`, all 3 `addfragments` and class loads | script compilation log plus class behavior | GZ/UZ/BD | NOT RUN |
| C-003 | BLOCKER | MAP01 GapNode → MAP02 Breach → MAP03 Warren | named transitions, no missing-target or fallback | GZ/UZ/BD | NOT RUN |
| C-004 | BLOCKER | Altar, ore, locator, weapon, DoomEdNum and sprite mapping | actual frames rendered and actor interactions | GZ/UZ/BD | NOT RUN |
| C-005 | BLOCKER | GLDEFS ELEC/ORESHA/TOOLA sprite-bound pointlights | side-by-side light-on/off scenes + logs | GZ/UZ/BD | NOT RUN |
| C-006 | BLOCKER | Godot producer → FPS handoff v1 | identical synthetic runId, seed, name at consumer/HUD | GZ/UZ/BD | NOT RUN |
| C-007 | BLOCKER | Custom `SNStatusBar` reacts to inventory and handoff | visual and numbers before/after pickup | GZ/UZ/BD | NOT RUN |
| C-008 | BLOCKER | Generated WAD header and semantics | validator report + unique in-game map marker | game packaging | NOT RUN |
| C-009 | HIGH | Save/load and next-map state | documented before/after inventory and identity | GZ/UZ/BD | NOT RUN |
| C-010 | HIGH | Backend selection/fallback | actual backend shown in log/OS, load & rendering | GZ/UZ/BD | NOT RUN |
| C-011 | HIGH | VOXELDEF-based prop/actor substitution | model visible, health/damage/collision unchanged | GZ/UZ/BD | NOT RUN |
| C-012 | HIGH | Dynamic-light workload and fallback | controlled counts, p50/p95/p99, profile comparisons | GZ/UZ/BD | NOT RUN |
| C-013 | MEDIUM | Curated third-party and shareware test set | lawful source rights and per-case behavior | GZ/UZ/BD | NOT RUN |
| C-014 | HIGH, SEPARATE | ZDaemon lane, no inferred ZScript or 3D-model parity | native ZDaemon evidence with scoped compatibility list | ZDaemon only | NOT RUN |
| C-015 | HIGH | Corrupt, stale, missing, boolean, future-schema handoff | explicit behavior and no secret exposure | GZ/UZ/BD | NOT RUN |

## Subcases to preserve

| ID | Associated case | Distinctive required negative/control test |
|---|---|---|
| C-002a | C-002 | remove or rename *fixture-only* fragment; prove error/fallback is detected |
| C-004a | C-004 | long sprite names `ORESHAA0` and `TOOLAA0` vs conventional four-char sprite prefix |
| C-005a | C-005 | definition present but attachment absent must not count as visible light |
| C-006a | C-006 | JSON booleans `hasParadox: true` and `false` in synthetic fixture |
| C-006b | C-006/C-015 | schema absent, schema newer, mismatched path, stale runId; **current reader is tolerant** |
| C-008a | C-008 | no assumption that generic WAD directory must start at offset 12; project generator format only |
| C-011a | C-011 | sprite→voxel only; keep actor script, hitbox, light binding unchanged |
| C-011b | C-011 | glTF geometry/animation, external textures and embedded `.glb` textures separately |
| C-012a | C-012 | 0, 2, 8, 16 lights as proposed *test sweep*, not shipped hard caps |
| C-009a | C-009 | snapshot/restore and revisits vs cosmetic seamless transition |
| C-015a | C-015 | no real private lineage data or actual Mantle vault mounts |

## Evidence contract

A valid result includes test case ID, engine/game SHA, exact binary/build identity, lawful IWAD reference (path/hash **not the IWAD**), PK3 hash, OS/driver/power mode, backend, resolution, graphics settings, deterministic scene/route, steps, raw failure lines, screenshots/video when needed, tester and date. **No evidence, no PASS.** Evidence from another machine cannot establish UHD 620 acceptance.

## Scheduling and authority

Execution requires separate operator authorization after work-order review. Local user runs engine/game; ChatGPT/agents do not run full engine builds or games. Consult `SNE-000C-TEST-CASE-CATALOG.md` before adopting any candidate.
