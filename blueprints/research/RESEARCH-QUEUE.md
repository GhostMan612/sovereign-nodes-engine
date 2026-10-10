# SNE Phase 00 research queue — WO-000E v0.7.0

All engine runtime, target build, legal clearance and performance gates remain **UNVERIFIED/NOT RUN**. The work-order publication history is not an acceptance record.

| ID | Priority | Required proof | Research state | Next owner role |
|---|---|---|---|---|
| R00-01 | P0 | pinned upstream game and engine source revision | selected pins VERIFIED | reviewer re-pin before execution |
| R00-02 | P0 | exhaustive game content/parser and actor inventory | PARTIAL source review | game maintainer/tester |
| R00-03 | P0 | transitive dependency and game-data/asset rights SBOM | PARTIAL | license reviewer |
| R00-04 | P0 | C-001…C-008 native per-engine game parity | NOT RUN | operator-controlled test |
| R00-05 | P0 | UZDoom upstream policy vs independent GPL fork | source-policy OBSERVED | legal/maintenance reviewer |
| R00-06 | P1 | actor-preserving voxel/glTF output and integration | source seams inspected; NOT RUN | rendering tester |
| R00-07 | P0 | 3-run UHD 620 trace per baseline/profile | NOT RUN | device operator |
| R00-08 | P1 | W1–W4 world continuity and save/transition state | DESIGN ONLY | gameplay tester |
| R00-09 | P0 | synthetic boolean and schema / path / replay handoff | suspected defects; NOT RUN | handoff/security tester |
| R00-10 | P1 | fork maintenance and controlled update trial | MODEL ONLY | maintainer |
| R00-11 | P1 | WO-A committed checksum independent validation | documented, not reviewed | independent reviewer |
| R00-12 | P1 | BiasedDoom GLTF ON, textures, skeletal animation | source and docs reviewed; NOT RUN | graphics tester |
| R00-13 | P0 | Windows compiler/SDK actual versions and successful build | NOT RUN | device operator |
| R00-14 | P0 | actual long sprite naming and GLDEFS association | HIGH-RISK HYPOTHESIS | gameplay tester |
| R00-15 | P0 | JSON `hasParadox` true/false wire behavior | HIGH-RISK HYPOTHESIS | gameplay tester |
| R00-16 | P1 | postFX, light workload and fallback frame times | SOP ONLY | device operator |
| R00-17 | P1 | separate ZDaemon feature and networking lane | NOT RUN | multiplayer tester |
| R00-18 | P0 | dependency hashes, binary provenance and resource packages | NOT RUN | build/asset reviewer |
| R00-19 | P0 | independent review of A–E and documented dissent | REQUESTED / NOT COMPLETED | independent reviewer |
| R00-20 | P0 | operator chooses foundation with recorded gates | **HOLD** | operator |
| R00-21 | P0 | explicit authorization for any source/build/benchmark | **NOT GRANTED** | operator |

**Ordered critical path:** reviewer cross-check → operator approves safe fixture/build scope → source game defect-isolation controls → candidate Windows builds → Tier-A parity → repeatable hardware traces → SBOM/security/maintenance review → signed ADR. Do not stage engine source modifications during WO-000E.
