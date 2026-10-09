# License and dependency review — preliminary, not legal sign-off

| Project | Main license evidence | Known build ecosystem | Outstanding diligence |
|---|---|---|---|
| GZDoom | README says GPLv3; https://github.com/ZDoom/gzdoom | CMake, platform libraries, bundled third parties | inspect exact LICENSE, per-file notices, bundled licenses, binary dependencies |
| UZDoom | README says GPLv3 or later; https://github.com/UZDoom/UZDoom | CMake; Windows/Linux/macOS build docs/wiki | inspect pinned LICENSE, submodules, assets, compatibility obligations and contributor policy |
| BiasedDoom | GZDoom-derived; GitHub license shown; https://github.com/EricsonWillians/BiasedDoom | CMake, fastgltf, embedded CPython in described implementation | inspect actual full license and each third party, CPython redistribution and model importer obligations |
| Chocolate Doom | GitHub labels GPL-2.0; https://github.com/chocolate-doom/chocolate-doom | Autotools/SDL family (documented) | inspect license text, Windows-specific libraries, binary packaging |
| Original Doom | source published; https://github.com/id-Software/DOOM | legacy C/portability | inspect specific code/license before copying any part |

## License hard gates

1. Engine code license vs GAME ASSETS license tracked separately.
2. Doom IWADs not bundled; original independent replacement assets or user-supplied legal IWAD required for runtime.
3. No vendor code copied into SNE planning scaffold.
4. If we distribute a derivative, assess corresponding source and notices required by GPL and bundled dependencies before release.
5. A project's policy against AI-generated contributions is distinct from its copyright license; external contributions or PRs must obey maintainer rules.
6. No final legal conclusion until exact pinned code, dependency manifest, notices and intended distribution are assessed by qualified reviewer.

## Research task

For every candidate, produce exact upstream commit, LICENSE/COPYING paths, submodule/dependency tree, Windows binary notices, content rights, and a license compatibility memo. Mark FAIL if any undocumented code/asset is proposed for packaging.
