# Phase 00 engine dependency and licensing review — v0.4.0

**Status:** Targeted source/license observations only, NOT distribution clearance or legal opinion. All package-specific bundled dependencies and assets require comprehensive SBOM review before release.

| Candidate | Code license basis | Build/dependency evidence | Assets and special notices | Remaining review |
|---|---|---|---|---|
| GZDoom | [GPL-3 license](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/LICENSE), numerous per-file BSD-style or LGPL notices | CMake >=3.16; C++17; root `vcpkg.json` features `vcpkg-libvpx`, `vcpkg-openal-soft` | `voxels.cpp` BSD-style notice, `models_voxel.cpp` LGPL-style | vendor subtrees, binary packaging, required notice preservation |
| UZDoom | [GPL-3+ main license](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/LICENSE), `CONTRIBUTING.md` requires GPLv3+ PR code | CMake >=3.16; C++20; `Python3` build dependency | [branding CC BY-SA 4.0](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/branding/BRANDING-LICENSE.md); `LICENSE` warns copyright-dependent `wadsrc_bm`, `wadsrc_extra`, `wadsrc_widepix` | rights of every bundled asset, all external packages, forks' credits |
| BiasedDoom | GZDoom-derived + mixed per-file terms; [`model_gltf.cpp` LGPL-2+](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/src/common/models/model_gltf.cpp) | CMake C++17; `fastgltf`; `vcpkg-python`/CPython 3.12.13 override; optional libs | materials, model workflows, icons/branding and possible texture rights need audit | dependencies transitivity, engine overall LICENSE, Python packaging and permissions |
| Chocolate Doom | CMake reports GPLv2; individual code headers GPLv2-or-later | C99; SDL2 >=2.0.14, SDL2_mixer >=2.0.2, SDL2_net >=2.0.0 | Doom IWAD is separate | not a production shortlist engine |
| Original Doom | README mentions GPLv2; historical file header may mention older release license | legacy C, historical dependency tree | no shipping copyrighted IWAD content | academic source study only |

## UZDoom contribution restrictions are not GPL restrictions

At pin `dbedcc894fb6866c48520cf27ae773f9957024b9`, [`CONTRIBUTING.md`](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/CONTRIBUTING.md) explicitly disallows AI-generated and AI-assisted code/comment submissions and art. We should not submit assistant-generated patches upstream. A separate properly licensed downstream fork is a different question; respect GPL terms and notices and research trade dress/branding independently.

## Distribution hard gates

1. No commercial Doom/Heretic/Hexen/Strife IWAD or other copyrighted game content in SNE ZIPs or its source repository.
2. Original SNE branding and art; no copied upstream logos without separately verified permission.
3. GPL source availability, copyright statements, patches and license inventory documented for any distributed derivative.
4. Third-party libraries and auxiliary asset folders independently reviewed; GPL root LICENSE does **not** imply every bundled image/asset is redistributable on identical terms.
5. Code borrowed from BiasedDoom, GZDoom or UZDoom requires exact original file license preservation and compatibility analysis.
6. No legal approval until full transitive SBOM, distribution model, source-offer mechanics and a qualified review are complete.
