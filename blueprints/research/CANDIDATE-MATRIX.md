# Phase 00 candidate matrix — v0.4.0 evidence update

**Status:** SOURCE CODE RESEARCH ONLY / foundation DECISION STILL PENDING. No candidate build/benchmark/compatibility PASS.

| Candidate | Source strength | Production suitability hypothesis | Observed risk | Next gate |
|---|---|---|---|---|
| GZDoom | Voxel/GLDEFS/ZScript/hub paths directly inspected; C++17 CMake | First production-baseline candidate | compiler/dependency details, modern glTF extensibility, measured GPU cost | native build + Tier-A pass |
| UZDoom | Same core systems at inspected revision; C++20, optional LTO | Second production-baseline candidate | upstream AI-code PR prohibition, build system differences, release asset rights | native build + Tier-A pass |
| BiasedDoom | `model_gltf` and CMake options inspected; fastgltf/optional CPython confirmed | Experimental rendering/model reference | ZScript deprecation intent, conditional codepaths, glTF embed-texture limitations, security/perf | glTF and ZScript runtime proof |
| Chocolate Doom | Original 2.5D logic and map loader, C99/SDL | Education/reference | no drop-in ZScript/high-end renderer | optional conceptual review |
| Original Doom | 1990s reference implementation | Education/reference | lacks modern assets/script/render systems | historical only |

## Scoring hold

Keep weighted scoring at **NOT SCORED** until operator-authorized Tier-A tests and GPU benchmarks exist. Published features are not benchmark scores. Reference rubric: 30% Tier-A, 20% maintainability/build, 15% low-end performance, 15% extensibility, 10% licensing/policy, 10% world/handoff feasibility.

## Provisional result

**GZDoom / UZDoom shortlist remains intact**; BiasedDoom merits a separate experimental comparison. Revisit after C/D work orders. ADR-SNE-002 is not adopted.
