# Foundation candidate matrix — WO-000E adversarial synthesis

**Decision: HOLD. Measurements: NONE. Scores: UNASSIGNED.** These are conditional source-informed hypotheses rather than observed operational rankings.

| Criterion | GZDoom | UZDoom | BiasedDoom |
|---|---|---|---|
| Source pin | `c26ce2e6ca2a` | `dbedcc894fb6` | `6147e0670458` |
| Existing ZScript/GLDEFS/voxel/hub source seams | OBSERVED | OBSERVED | inherited/doc claims; exact parity NOT RUN |
| Toolchain declaration | CMake ≥3.16 / C++17 | CMake ≥3.16 / C++20 | CMake ≥3.16 / C++17 |
| Modern glTF / skeletal models | native support not proven at pin | native support not proven at pin | conditional fastgltf implementation; runtime NOT RUN |
| Embedded Python | not established gameplay runtime | Python3 required for build utilities, not gameplay proof | optional, explicitly **not sandboxed** |
| AI-assisted contributions | verify upstream submission policies if applicable | explicitly prohibited for upstream code/art contributions | project docs encourage disclosed, reviewed AI assistance |
| P0 game parity C-001–C-008 | NOT RUN | NOT RUN | NOT RUN |
| UHD 620 frame-time | NOT MEASURED | NOT MEASURED | NOT MEASURED |
| Complete license/SBOM and assets | NOT CLEARED | NOT CLEARED | NOT CLEARED |
| Recommended research role | first **test control** | independent production **comparator** | feature **reference** |

## Disqualifying requirements before weighted scoring

- Prove exact custom MAP01, scripts/actors/HUD, GLDEFS, map transitions, synthetic handoff and validated resources using C-001…C-008.
- Record complete lawful dependency/asset rights and executable provenance.
- Collect operator-authorized same-scene UHD 620 measurements with raw frame-time traces and environment controls.
- Obtain independent technical and license review plus operator decision.

## Scorecard (intentional empty values)

| Weight | Dimension | GZDoom | UZDoom | BiasedDoom |
|---|---|---|---|---|
| 30% | Tier-A actual parity | — | — | — |
| 20% | Build, maintenance and updateability | — | — | — |
| 15% | Measured low-end performance | — | — | — |
| 15% | Extensibility without baseline breakage | — | — | — |
| 10% | Rights, licensing and policy sustainability | — | — | — |
| 10% | World/handoff feasibility and security | — | — | — |

No weights can overcome a failed hard gate. A source feature is not a runtime score. Detailed alternatives: `SNE-000E-ALTERNATIVES-ANALYSIS.md`.
