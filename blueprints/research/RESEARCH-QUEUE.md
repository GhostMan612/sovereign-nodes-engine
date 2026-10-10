# SNE-P00 Research and closure queue — WO-000F v0.8.0

**Source-review state only; no local engine tests, device measurements or legal clearance were performed by WO-000F.** Historic A–E records remain unchanged.

| ID | Priority | Proof needed | State | Proposed closure lane |
|---|---|---|---|---|
| R00-01 | P0 | Immutable game/upstream pins checked by independent reviewer | SOURCE PINNED / RECHECK PENDING | F-00 |
| R00-02 | P0 | Actual packaged game classes/lumps exhaustive audit | PARTIAL | F-02 |
| R00-03 | P0 | Transitive library and asset-rights SBOM | PARTIAL / NOT CLEARED | F-06 |
| R00-04 | P0 | C-001…C-008 per candidate with negative controls | NOT RUN | F-04 |
| R00-05 | P0 | UZDoom policy and maintainable downstream workflow | SOURCE OBSERVED / OWNER REVIEW PENDING | F-06 |
| R00-06 | P1 | Voxels, glTF/GLB animation runtime and parity | NOT RUN | F-05 |
| R00-07 | P0 | Three-run UHD 620 P0 traces | NOT RUN | F-05 |
| R00-08 | P1 | Logical zone save/revisit/state semantics | NOT RUN | F-05 |
| R00-09 | P0 | Boolean/schema/stale handoff threat tests | NOT RUN | F-02/F-04 |
| R00-10 | P1 | Fork conflict/update trial | NOT RUN | F-06 |
| R00-11 | P1 | WO-A checksum independent review | DOCUMENTED / REVIEW PENDING | F-00 |
| R00-12 | P1 | BiasedDoom glTF ON and Python OFF proof | NOT RUN | F-05 |
| R00-13 | P0 | Windows MSVC/CMake/SDK actual compiler build | NOT RUN | F-03 |
| R00-14 | P0 | Sprite identity `ORESHAA0`, `TOOLAA0`, GLDEFS | HIGH-RISK SOURCE HYPOTHESIS | F-02 |
| R00-15 | P0 | Godot boolean `hasParadox` vs ZScript `ScanInt` | HIGH-RISK SOURCE HYPOTHESIS | F-02 |
| R00-16 | P1 | GPU dynamic-light/postFX/fallback frame times | NOT RUN | F-05 |
| R00-17 | P1 | ZDaemon separately pinned and tested | NOT RUN | SEPARATE LANE |
| R00-18 | P0 | Dependency, binary/resource and game artifact hashes | NOT RUN | F-03/F-06 |
| R00-19 | P0 | Independent A–F reviewer dissent and resolution | NOT COMPLETED | F-00/F-07 |
| R00-20 | P0 | Operator evidence-backed foundation choice | **HOLD** | F-07 |
| R00-21 | P0 | Explicit work-category authorization before local testing | **NOT GRANTED** | F-01 |
| R00-22 | P0 | Verify actual `validate_pk3.py` path; source comments reference it, direct pinned path lookup failed | DISCREPANCY / NOT PROVEN | F-00/F-02 |
| R00-23 | P0 | Baseline identity (original PK3, control engine and lawful IWAD) before diagnosis | NOT CAPTURED | F-02 |
| R00-24 | P0 | Distinguish source-game defect from candidate regression with fixture-only controls | SPECIFIED / NOT RUN | F-02/F-04 |
| R00-25 | P1 | Validate raw frametime timestamps and equal rendered scene before scoring | NOT RUN | F-05 |
| R00-26 | P0 | Each C-series claim linked to one result and reviewer decision | NO RESULTS | F-04/F-07 |

**Stop order:** no score before C-001 proof; no profile performance claim before real device trace; no ADR adoption while any mandatory G1–G8 evidence is absent.
