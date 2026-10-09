# SNE-WO-000B — Source-level code map

**Pinned revisions:** see `evidence/sources/SNE-SOURCE-PINS-000B.md`.
**Status:** Confirmed file-level ownership and selected symbols; call graph and full source coverage NOT COMPLETE.

| SNE system | GZDoom starting path | UZDoom starting path | BiasedDoom starting path | Research conclusion |
|---|---|---|---|---|
| Boot/archives | `src/d_main.cpp` | `src/d_main.cpp` | inherited engine loader, not deeply traced | WAD/PK3 discovery likely reuse; verify exact mount priority |
| Actor scripting | `src/scripting/thingdef.cpp`; `src/scripting/zscript/` | corresponding `thingdef.cpp`, `zcc_compile_doom.cpp` | ZScript inherited according to README | **Do not replace VM** just to add rendering features |
| Voxel load | `src/common/models/voxels.cpp` | same-path `voxels.cpp` | inherited by claim | Resource loader already exists for voxels |
| Voxel placement | `src/r_data/voxeldef.cpp` | verify matching `VOXELDEF` parser | inherited by claim | Sprite/frame association supports replacement assets |
| Voxel draw | `src/common/models/models_voxel.cpp` | expected inherited path; not fully traced | inherited by claim | Use model interface; avoid making voxel physics synchronous with rendering |
| Dynamic lights | `src/r_data/gldefs.cpp` | `src/r_data/gldefs.cpp` | inherited plus custom controls | Existing actor/frame light association is primary seam |
| Model import | `src/common/models/` | `src/common/models/` | `src/common/models/model_gltf.h/.cpp` | BiasedDoom adds guarded glTF loader, not automatically portable |
| Hub-state | `src/g_hub.cpp` | `src/g_hub.cpp` | inherited not traced | Serial state supports logical continuity; not proof of simultaneous zone streaming |
| Save/persistence | `src/g_hub.cpp` includes `serializer.h` | same | undecided | Do not change save serialization format in Phase 01 |
| Renderer | `src/rendering/hwrenderer/` paths referenced by includes | similar source organization | additional rendering paths per docs | Backend modernization is deferred until profile proves need |
| Build | root `CMakeLists.txt` and `vcpkg.json` | root CMake | root CMake, vcpkg features | Must pin actual build toolchain before selecting fork |

## Required contracts from Sovereign Nodes FPS

At game SHA `44034e97fd22129f919a18cadceb84466ef1bcd3`:

- `game/MAPINFO.txt`: `version "4.14"` precedes three `addfragments`; maps `MAP01` GapNode → `MAP02` Breach → `MAP03` Warren. Test **actual custom map identity**, not simply a Doom window opening.
- `game/GLDEFS.txt`: `ELEC`, `ORESHA`, `TOOLA` lights attached to frames `ELECA0`, `ORESHAA0`, `TOOLAA0` plus fog. Packaging roots must be verified.
- `zscript/core.zs`, `hud.zs`, `doomednum.txt`: ore/altar/enemy class semantics, `SNStatusBar`, Editor thing identifiers; preserve class compatibility.
- `src/world/fps_launcher.gd` + `zscript/sn_handoff.zs`: Godot writes JSON `schema=1`, run/ancestor fields to `%TEMP%/SovereignNodes/fps_handoff.json`; ZScript reads. Handoff is **not** authorization to expose real personal data to test fixtures.
- Build scripts `build_pk3.py`, `build_maps.py`, `validate_wads.py` are project-local safeguards. The generator's `dirofs=12` is **this generator's enforced layout**, not a universal rule requiring all valid WADs to have directory offset 12.
- Separate ZDaemon gameplay compatibility is a different execution lane. Do not conflate GZDoom ZScript capabilities with ZDaemon capabilities.

## Unknown interfaces / action requests

1. Which engine owns the model registration and GPU buffer lifecycle from `VOXELDEF` to renderer submission?
2. Can an SNE wrapper extend material import without touching serialized actors or multiplayer state?
3. Are `GLDEFS` per-sprite associations identical across candidate revisions at runtime?
4. Which ZScript APIs are actually available in current-game handoff code and what are its failure semantics?
5. Does the Godot producer's JSON `hasParadox: true/false` correctly parse through the Doom-side `ScanInt`/`ToInt` path? **Suspected issue, not yet reproduced.**
6. Are per-map hub state and ordinary `next`/cluster transitions sufficient for desired continuity before any streaming?

## Strategy

Build adapters **around** proven upstream systems. Require before/after user-visible regression cases for each extension. No independent renderer, ZScript fork, chunk streaming, voxel-terrain engine or direct Mantle graph read in Phase 01.
