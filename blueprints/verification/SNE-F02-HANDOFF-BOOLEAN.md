# F-02B — JSON boolean wire truth table and parser discrimination

## Source-observed interfaces

- Godot `games/SovereignNodes/src/world/fps_launcher.gd` serializes `hasParadox` with `bool(...)` through `JSON.stringify(payload, "\t")`.
- ZScript `games/SovereignNodesFPS/zscript/sn_handoff.zs` obtains the raw token via `ScanRaw`, then `ScanInt`, `s.ToInt(0, out)` and `paradoxFlag != 0`.
- Actual ZScript `ToInt("true"/"false")` behavior and `paradoxFlag` initialization are **unverified**; test both positives and negatives, never infer that false default implies correct parsing.

| ID | Synthetic input | Expected truth-table contract | Evidence status |
|---|---|---|---|
| H-B01 | v1 `hasParadox: true`, `SAMPLE ANCESTOR A`, seed 42 | consumer true, HUD shows paradox | NOT RUN |
| H-B02 | v1 `hasParadox: false`, otherwise same seed/runId | consumer false, no paradox marker | NOT RUN |
| H-B03 | fixture-only numeric `hasParadox: 1` | observe numeric parser branch; cannot certify Godot original | NOT RUN |
| H-B04 | fixture-only numeric `hasParadox: 0` | control false representation; detect default ambiguity | NOT RUN |
| H-B05 | missing key or null variant | bounded safe behavior; explicitly record absent default | NOT RUN |
| H-B06 | bool true with updated fresh runId, schema unchanged | compare fresh vs stale and collision semantics | NOT RUN |

**Control policy:** B0 is Godot's *actual* boolean-producing flow; B2 is a distinct synthetic JSON mutation fixture, each with raw hash. No real person graph, Mantle vault, personal names or private runId. `AUTH-F` to create B2, `AUTH-T` to launch/read in a game; no execution authority in this ZIP.
