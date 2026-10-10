# F-00 — Immutable pinned evidence and author-inspected blobs

**Date inspected:** 2026-10-09. **Mode:** read-only connected GitHub file retrieval; author recheck, not independent reviewer. **No game/engine builds, launches or benchmarks.**

| Repository | Exact commit | Purpose |
|---|---|---|
| [SNE planning](https://github.com/GhostMan612/sovereign-nodes-engine/commit/1c01d2ff5bc3a1369210a7d68dd58269ecf6506d) | `1c01d2ff5bc3a1369210a7d68dd58269ecf6506d` | v0.9.0 ZIP preimage; WO-F published |
| [Sovereign-Nodes](https://github.com/GhostMan612/Sovereign-Nodes/commit/44034e97fd22129f919a18cadceb84466ef1bcd3) | `44034e97fd22129f919a18cadceb84466ef1bcd3` | original game source claims |
| [GZDoom](https://github.com/ZDoom/gzdoom/commit/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7) | `c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7` | first control source only |
| [UZDoom](https://github.com/UZDoom/UZDoom/commit/dbedcc894fb6866c48520cf27ae773f9957024b9) | `dbedcc894fb6866c48520cf27ae773f9957024b9` | second comparator source only |
| [BiasedDoom](https://github.com/EricsonWillians/BiasedDoom/commit/6147e0670458e48e63d1a40750f36dfc68b00f7f) | `6147e0670458e48e63d1a40750f36dfc68b00f7f` | experimental reference source only |

## Exact reviewed Git blob SHA-1s

| Path qualified by repository | Git blob SHA-1 |
|---|---|
| Game `games/SovereignNodesFPS/game/MAPINFO.txt` | `c26536e370e70376d47c35d9c984ef7db6d0215e` |
| Game `games/SovereignNodesFPS/game/GLDEFS.txt` | `b98abc8de454617fc5681fb585ac8d41cee71bc9` |
| Game `games/SovereignNodesFPS/zscript/core.zs` | `61fb41c797d909404153d77bab894704637ceba4` |
| Game `games/SovereignNodesFPS/zscript/sn_handoff.zs` | `c83a8058d602ee6d1c6a7aca2792a5d408db2ebb` |
| Game `games/SovereignNodes/src/world/fps_launcher.gd` | `7bbd446af0fb3e9c7f8e2646863101e06fc23f3a` |
| Game `games/SovereignNodesFPS/tools/build_pk3.py` | `547c1f552de2e60373c112d7fd3a8717a72ae4db` |
| Game `games/SovereignNodesFPS/tools/validate_wads.py` | `cff34dc0934568ab7311b9cdc062a92743e78a77` |
| GZDoom `src/r_data/sprites.cpp` | `0a7be96a12003a4996b0ea1ca2b275eec6840785` |
| GZDoom `CMakeLists.txt` | `8a1becdb8546036d117f63db0a18c5a45541a8ba` |
| UZDoom `CMakeLists.txt` | `39dcbefed262eab124f23da8efdb7b3ce331dcd9` |
| UZDoom `CONTRIBUTING.md` | `84621215c99b1da9af913d082e65e20b6d725175` |
| BiasedDoom `CMakeLists.txt` | `ac506cbca31c2702af87011e1b7fd83e1839813c` |

## Failed-path evidence

Direct fetch of game `games/SovereignNodesFPS/tools/validate_pk3.py` at `44034e97fd22129f919a18cadceb84466ef1bcd3` returned 404/NOT_FOUND. This is not evidence of a failed local test, nor global absence of an equivalent implementation. A distinct reviewer must independently inspect the complete pinned tree and references, and can correct the path-level conclusion if counterevidence appears.

## Revalidation obligation

Every table row describes immutable *historical pinned source*, not latest GitHub HEAD or present locally installed binaries. A future actual experiment must record its own source revision, executable hash and resource hash. Independent reviewer rechecks key claims from primary source and records dissent; historical WO-A…F evidence remains unchanged.
