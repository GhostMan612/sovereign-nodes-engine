# SNE-SRC-GZDOOM-003 — Sprite, voxel and world seam review

- Repo: `ZDoom/gzdoom`
- Pin: `c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7`
- Classification: CODE READ, SOURCE-OBSERVED; NO COMPILATION.

## Evidence

- `src/r_data/sprites.cpp`, `R_InitSpriteDefs()`: indexes family from the initial 4 characters and uses `GetName()[4]` for frame and `[5]` for rotation. Inference: long frame names in current game risk parsing differently than intended. Test with actual packaged PK3; do not treat static detection as proof of a visible defect.
- `src/r_data/voxeldef.cpp`, `R_InitVoxels()`: scans VOXELDEF lump; `VOX_ReadSpriteNames` accepts four-character sprite family or five including frame. Associates KVX from the voxel namespace. This is actor visual substitution, not general world streaming.
- `src/common/models/models_voxel.cpp` and `voxels.cpp`: inherited voxel/model processing; real hardware budget untested.
- `src/r_data/gldefs.cpp`: parses light defaults and actor/frame bindings; game GLDEFS validity untested in binary.
- `src/g_level.cpp` and `g_hub.cpp`: stateful level transitions/hub support. Not proof of rendering two maps concurrently.

## Immutable links

- [sprite resolver](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/src/r_data/sprites.cpp)
- [VOXELDEF scanner](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/src/r_data/voxeldef.cpp)
- [voxel model manager](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/src/common/models/models_voxel.cpp)
- [GLDEFS parser](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/src/r_data/gldefs.cpp)
- [level change](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/src/g_level.cpp)
- [hub](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/src/g_hub.cpp)

## Follow-up

Run C-001..C-012 under operator approval with fixed PK3/driver/renderer. Dynamic lighting, actor sprite names and handoff booleans must be checked against an exact executable. No direct engine modification authorized.
