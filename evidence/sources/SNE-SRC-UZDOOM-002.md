# SRC-UZ-002 — UZDoom implementation and policy observations

**Pin:** `dbedcc894fb6866c48520cf27ae773f9957024b9`
**Class:** Direct selected source/license/contribution-policy inspection.
**Not built, launched, profiled, or approved for upstream contribution.**

| Concern | Source evidence | Conclusion |
|---|---|---|
| Build | [CMakeLists.txt](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/CMakeLists.txt) | CMake 3.16 minimum, C++20, optional LTO. `find_package(Python3 3.6 REQUIRED)` is a build dependency; **does not mean embedded gameplay Python** |
| ZScript | [thingdef.cpp](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/src/scripting/thingdef.cpp) and [zcc_compile_doom.cpp](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/src/scripting/zscript/zcc_compile_doom.cpp) | Actor compiler paths exist; `sn_handoff.zs` runtime integration remains UNTESTED |
| Voxels | [voxels.cpp](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/src/common/models/voxels.cpp) | Palette remap/voxel loader path inherited; parity relative to GZDoom not tested |
| GLDEFS | [gldefs.cpp](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/src/r_data/gldefs.cpp) | Light parser and associations are present; GZDoom API similarity visible, not guaranteed ABI/API identity |
| World hub | [g_hub.cpp](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/src/g_hub.cpp) | Preserves `G_LeavingHub` / hub state pattern, not streaming world proof |
| Engine licensing | [LICENSE](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/LICENSE) | GPL-3-or-later main license; repository carries explicitly different licenses on assets, branding and legacy code |
| Branding | [branding/BRANDING-LICENSE.md](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/branding/BRANDING-LICENSE.md) | Branding CC BY-SA 4.0, distinguish from engine code; prefer original SNE branding |
| Contribution rule | [CONTRIBUTING.md](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/CONTRIBUTING.md) | Prohibits AI-generated/assisted PR code, comments, and generated art. No AI-authored upstream PR should be attempted |

## Critical separation: upstream policy vs licensing

The maintainer's rule governs what they will accept into UZDoom. The GPL license governs reuse and redistribution of GPL-covered code. A private/local fork or separate publicly distributed GPL-compliant derivative is not automatically forbidden just because AI assistance is used; however, we must separately review licenses, notices, marks, third-party assets, and whether intended distribution is compatible. Avoid conflating permissions to fork with permissions to contribute upstream. This is planning analysis, **not legal advice or final license clearance**.

## Recommendation

UZDoom remains on the compatibility-first shortlist, but the SNE agent workflow makes upstream contribution inadmissible without independently authored, policy-compliant work. Plan a low-diff downstream fork if selected; measure its update/merge cost against GZDoom.

## Unresolved

- Exact supported Windows compiler/toolchain and package availability on target Dell.
- Tier-A ZScript/MAPINFO/GLDEFS/handoff runtime behavior.
- Full non-engine assets and dependency license inventory; all-in-one binary distribution permissions.
- Performance comparison with GZDoom/experimental branch on UHD 620.
