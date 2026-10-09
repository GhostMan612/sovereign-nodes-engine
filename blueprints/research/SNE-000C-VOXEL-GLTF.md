# SNE-WO-000C — Voxel and glTF feasibility / staged model adoption

## Findings by engine (source observations, NOT implementation proof)

| Candidate | Inherited path | Incremental first step | Unproven extension |
|---|---|---|---|
| GZDoom | `src/r_data/voxeldef.cpp`, `src/common/models/voxels.cpp`, `models_voxel.cpp`, `src/r_data/sprites.cpp` | add fixture-only conventional KVX and VOXELDEF for a sprite family | arbitrary voxels/marching-cube world geometry |
| UZDoom | analogous `voxeldef.cpp`/`voxels.cpp` and rendering | same sprite→voxel fixture | exact backend parity and performance |
| BiasedDoom | inherited voxels; conditional `src/common/models/model_gltf.cpp` and `fastgltf` | compare external-texture `.gltf + .bin` and `.glb` | robust embedded texture upload and lower-end GPU cost |

## Source-level model constraints

GZDoom's `VOXELDEF` parser maps 4- or 5-character sprite-family references (5 adds frame character) to KVX voxel definitions in a `/voxels/` namespace. This is not a general-purpose voxel terrain system, nor is actor collision automatically replaced by voxel surface collision. The initial target must be a prop or actor *visual replacement* only.

BiasedDoom's CMake enables glTF with `BIASEDDOOM_ENABLE_GLTF` and requires `fastgltf`; its source wraps glTF loader in `NEODOOM_GLTF_SUPPORT`. Confirm actual macro assignment/registration in a pinned build. Its docs recommend `.gltf + .bin + external textures` and warn that embedded `.glb` texture behavior has limits; model geometry, skeleton, PBR material, texture upload and save/reload need separate proof.

## Proposed non-destructive fixture ladder

1. V0: original sprite baseline; confirm actor name, health, collision, pickup/damage interaction, screenshots.
2. V1: one static KVX pickup with `VOXELDEF` mapped to a conventional four-char sprite family; compare actor state, rotations and lighting.
3. V2: one animated enemy using unchanged ZScript actor logic but changing only presentation; confirm hitbox and damage unaffected.
4. V3: conditional BiasedDoom glTF static external-texture asset; visual+material+load control.
5. V4: glTF animated asset with skeletal transitions, missing texture errors and embedded `.glb` negative/positive separately.
6. V5: randomized/over-budget models and malformed asset test *after safe fixture and build authorization*.

## Performance design

Use 720p UHD 620 P0–P3 profiles with model counts 0/1/8/32 as candidate *test probes* (not established shipping limits). Capture GPU/CPU frame times and memory. Large model count, PBR and skeletal animation must be individually toggled to isolate cost.

## Exclusions

No original game changes in this overlay; no 3D physics rewrite, render-through inter-map portals, voxels as world BSP replacement, glTF guarantee on stock GZDoom, or unrestricted embedded Python for model mods.

GZDoom voxel parser: https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/src/r_data/voxeldef.cpp
UZDoom voxel parser: https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/src/r_data/voxeldef.cpp
BiasedDoom glTF loader: https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/src/common/models/model_gltf.cpp
BiasedDoom docs: https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/docs/gltf/README.md
