# SNE-SRC-UZDOOM-003 — Compatibility and source seam review

- Repo: `UZDoom/UZDoom`
- Pin: `dbedcc894fb6866c48520cf27ae773f9957024b9`
- Classification: SELECTED SOURCE READ; NO COMPILE/GAME.

## Observed code

- `src/r_data/voxeldef.cpp` exposes a sprite-family-to-voxel parsing path akin to GZDoom; `src/common/models/voxels.cpp` manages voxel data.
- `src/r_data/gldefs.cpp` includes default light and sprite/frame association methods; actual three authored game lights untested.
- `src/scripting/thingdef.cpp` performs actor/state finalization, weapon/inventory validation; exact game ZScript compile untested.
- `src/g_level.cpp` and `g_hub.cpp` implement game level/hub machinery; they do not demonstrate multi-map continuous space.
- `CONTRIBUTING.md` explicitly bans AI-assisted submissions upstream. Distinguish contributor policy from GPL redistribution rights; private fork feasibility remains subject to licensing review.

## Immutable links

- [voxeldef](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/src/r_data/voxeldef.cpp)
- [voxel data](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/src/common/models/voxels.cpp)
- [GLDEFS](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/src/r_data/gldefs.cpp)
- [ZScript thingdef](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/src/scripting/thingdef.cpp)
- [level](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/src/g_level.cpp)
- [hub](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/src/g_hub.cpp)
- [contributions](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/CONTRIBUTING.md)

## Known work

Source code version only; project C++20 build/runtime and UHD 620 must be independently verified. No definitive foundation selection is made here.
