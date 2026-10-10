# WO-F — Frozen source and document revision ledger

**Review date:** 2026-10-09. **Scope:** read-only GitHub source inspection, NOT target machine test, no claims of latest upstream commits. Pin entire source revision plus path; source files may evolve later. The effective future test revisions must be recorded anew before execution.

| Identity | Pinned commit | Used for |
|---|---|---|
| [`GhostMan612/sovereign-nodes-engine`](https://github.com/GhostMan612/sovereign-nodes-engine/commit/1644fb80c3e2803dd19465292423832e8fdf8e24) | `1644fb80c3e2803dd19465292423832e8fdf8e24` | overwrite/base checks |
| [`GhostMan612/Sovereign-Nodes`](https://github.com/GhostMan612/Sovereign-Nodes/commit/44034e97fd22129f919a18cadceb84466ef1bcd3) | `44034e97fd22129f919a18cadceb84466ef1bcd3` | MAPINFO/GLDEFS/ZScript/handoff/tools |
| [`ZDoom/gzdoom`](https://github.com/ZDoom/gzdoom/commit/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7) | `c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7` | first proposed control source |
| [`UZDoom/UZDoom`](https://github.com/UZDoom/UZDoom/commit/dbedcc894fb6866c48520cf27ae773f9957024b9) | `dbedcc894fb6866c48520cf27ae773f9957024b9` | independent production comparator source |
| [`EricsonWillians/BiasedDoom`](https://github.com/EricsonWillians/BiasedDoom/commit/6147e0670458e48e63d1a40750f36dfc68b00f7f) | `6147e0670458e48e63d1a40750f36dfc68b00f7f` | experimental model/Python source |

## WO-F source checks and classifications

| Claim | Immutable source location | Kind | Observed / limit |
|---|---|---|---|
| MAPINFO custom 3-map progression | [game MAPINFO](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/game/MAPINFO.txt) | SOURCE-OBSERVED | version 4.14, three fragment references, three map declarations; not actual runtime |
| Long sprite names and frame constants | [game core.zs](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/zscript/core.zs) | SOURCE-OBSERVED | ORESHAA0, TOOLAA0; outcome unknown |
| Light association names | [game GLDEFS](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/game/GLDEFS.txt) | SOURCE-OBSERVED | texture values include ORESHAA0 / TOOLAA0; emission not proven |
| Boolean producer | [fps_launcher.gd](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodes/src/world/fps_launcher.gd) | SOURCE-OBSERVED | hasParadox emitted via bool() |
| Integer-oriented consumer | [sn_handoff.zs](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/zscript/sn_handoff.zs) | SOURCE-OBSERVED | ScanInt on KEY_PARADOX; truth-table runtime unverified |
| Sprite lookup convention | [GZDoom sprites.cpp](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/src/r_data/sprites.cpp) | SOURCE-OBSERVED | family prefix/frame loading suggests risk, not proven error |
| Game packager references `validate_pk3.py` | [build_pk3.py](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/tools/build_pk3.py) | SOURCE-OBSERVED | path `games/SovereignNodesFPS/tools/validate_pk3.py` not found in pinned snapshot lookup; verify real validator location |
| Game WAD validator exists | [validate_wads.py](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/tools/validate_wads.py) | SOURCE-OBSERVED | existence not successful run |

## Document preimage guard

SNE base is exactly `1644fb80c3e2803dd19465292423832e8fdf8e24`. The six intentional REPLACE paths and their Git blob SHA-1s are listed in `scaffold/WO-000F-MANIFEST.md` and `scaffold/WO-000F-FILE-SHA256.json`. These preimages are for content equivalence, not a proof that the local worktree is clean. No GitHub repository was edited by the research author.

## Missing evidence

No original generated PK3 SHA-256, real IWAD rights check, engine binary hash or OS/toolchain inventory, C-series run, UHD trace, comprehensive SBOM or qualified independent reviewer signoff. Historic source records from WO-A…WO-E remain authoritative for their respective dates/scopes.
