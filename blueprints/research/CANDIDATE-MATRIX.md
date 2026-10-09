# Engine candidates — pinned-source preliminary matrix

**No winner chosen. No scores until runtime and legal gates pass.** Revision details: `evidence/sources/SNE-REVISION-LEDGER.md`.

| Candidate | Source observed | Main strength | Main constraint | Lane |
|---|---|---|---|---|
| GZDoom | C++17 CMake; voxel files; ZScript compiler; GLDEFS parser | High compatibility reference; minimal porting | Future upstream and exact runtime baseline need measurement | PRODUCTION CANDIDATE |
| UZDoom | C++20 CMake; Python3 build dependency; ZScript/voxel source | Active GZDoom-family direction | No AI-assisted upstream PRs; asset-specific license exceptions | PRODUCTION CANDIDATE WITH GOVERNANCE RISK |
| BiasedDoom | Conditional `model_gltf.cpp` with fastgltf; Python/glTF flags | Modern animation/materials experiment | Experimental scope; ZScript roadmap; security/performance | EXPERIMENTAL CANDIDATE |
| Chocolate Doom | C99/SDL2, WAD/BSP/collision source | Readable original algorithms | Lacks modern ZScript expectations | REFERENCE ONLY |
| Original Doom | BSP/sector/BLOCKMAP reference in historical Linux code | Design archaeology | No modern port/engine integration | REFERENCE ONLY |

## Decision model (unscored)

- Sovereign Nodes Tier-A parity — 30 points
- Build reproducibility/merge effort — 20 points
- Real UHD 620 benchmarks — 15 points
- Lighting/voxel/glTF extensibility — 15 points
- Licensing and team contribution governance — 10 points
- World/handoff architecture — 10 points

**Hard stops:** Tier-A parity failure, unresolved redistribution licensing, unusable measured performance, or unsafe Mantle boundary. No conclusion from README feature lists alone.

Root GPL text is not a complete third-party/asset-license review. UZDoom policy controls contributions *to their upstream*, not blanket restrictions on license-compliant SNE independent fork development.
