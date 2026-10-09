# SNE Phase 00 research queue — v0.5.0

**Date:** 2026-10-09. Evidence states are specific; blueprint completion does not equal runtime acceptance.

| ID | Priority | Question | Status after WO-000C source/spec pass | Next authoritative proof |
|---|---|---|---|---|
| R00-01 | P0 | Pin revisions | SOURCE-COMPLETE FOR LISTED REVISIONS | refresh if baseline/release changes |
| R00-02 | P0 | Game interfaces | SOURCE-ADVANCED / NOT EXHAUSTIVE | verify class symbol inventory in local full repo |
| R00-03 | P0 | GPL/component/asset licensing | PARTIAL | complete dependency/asset SBOM and review |
| R00-04 | P0 | ZScript/MAPINFO compatibility | TESTS SPECCED / NOT RUN | per-candidate engine runtime proof |
| R00-05 | P0 | UZDoom source/policy | SOURCE-OBSERVED | verify operator fork/patch policy and build |
| R00-06 | P1 | Voxel and glTF extension | SOURCE-OBSERVED / PROBES SPECCED | model/texture registration runtime tests |
| R00-07 | P1 | UHD 620 | BENCHMARK PLAN EXPANDED / NOT RUN | operator three-run captures |
| R00-08 | P1 | World continuity | FOUR-STAGE DESIGN / NOT TESTED | map-state save/load and hub proof |
| R00-09 | P0 | Handoff + Mantle security | SOURCE CONCERNS DOCUMENTED | boolean, schema, replay, bounds tests |
| R00-10 | P1 | Fork maintenance cost | RESEARCH ONLY | executable diff/update exercise later |
| R00-11 | P0 | WO-000A checksum | DOCUMENTED RECONCILIATION IN WO-B | operator independent checksum verification |
| R00-12 | P1 | BiasedDoom conditional glTF | SOURCE-OBSERVED / NOT RUN | glTF/GLB fixture probe |
| R00-13 | P1 | UZDoom C++20 toolchain | SOURCE-OBSERVED / NOT RUN | authorized Windows build |
| R00-14 | P0 | Sprite prefix/name mismatch | HIGH-RISK SOURCE FINDING | compare packed sprite decode/actor state in engine |
| R00-15 | P0 | Godot→Doom boolean and schema handling | HIGH-RISK SOURCE FINDING | synthetic JSON truth-table test |
| R00-16 | P1 | Performance profile budgets | WRITTEN / NOT MEASURED | UHD 620 standardized run |
| R00-17 | P1 | ZDaemon compatibility separation | SPECIFIED / NOT TESTED | native ZDaemon test lane |

**Progression:** WO-000C blueprint review → operator acceptance of test plan → separately authorize measurement/build work → WO-000D hardware/build plan → WO-000E foundation ADR review. Do not promote source findings to PASS.
