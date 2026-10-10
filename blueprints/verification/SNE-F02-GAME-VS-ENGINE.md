# F-02 — Game-content defect vs engine regression: falsifiable classification

| Observation, later | Initial classification | Required countercheck |
|---|---|---|
| B0 fails same case on GZDoom and UZDoom; B1 one-change fixture repairs both | `POSSIBLE GAME/PK3 DEFECT` | identical legal resources, two engine binaries, fixture diff; reviewer source audit |
| B0 passes control candidate; fails comparator at same PK3 and IWAD identity | `POSSIBLE ENGINE COMPATIBILITY REGRESSION` | backend flags/build hashes/diagnostics and repeatability |
| B0 fails; B1 passes only one engine | `MIXED / INCONCLUSIVE` | isolate parser/asset rules and any fixture confounds |
| Both pass B0 | `POSSIBLE PARITY` | still require C-001…C-008 actual negative controls and reviewer |
| One or both engines boot stock Entryway | `INVALID GAME IDENTITY` | detect unique GapNode marker; do **not** score FPS or graphics |
| Handoff false works but true fails | `POSSIBLE BOOL PARSER DEFECT` | compare native Godot producer boolean and numeric-only fixture |
| Sprite PNG exists yet invisible | `POSSIBLE LOADER/BINDING DEFECT` | actual actor class, frame registration and texture associations |
| Tool / lawful IWAD / signed AUTH missing | `BLOCKED` | do not claim engine failure |

Every classification is conditional on **future authorized actual evidence** and correction/dissent review. The original game remains untouched. When the defect belongs to game content, propose a separately authorized repair work order and retain unmodified B0 as a failing historical observation.
