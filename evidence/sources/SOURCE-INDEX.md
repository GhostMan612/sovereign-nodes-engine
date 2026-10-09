# Phase 00 source ledger — seed

Collected: 2026-10-09. No upstream source trees cloned. No engine builds run. Some source inspection used the connected GitHub repository reader. All Git refs must be pinned before formal acceptance.

| ID | Type | Location | Status |
|---|---|---|---|
| SRC-01 | Official upstream repo/readme | https://github.com/UZDoom/UZDoom | READ (README scope) |
| SRC-02 | Official upstream repo/readme | https://github.com/ZDoom/gzdoom | READ (README scope) |
| SRC-03 | Upstream experimental repo/readme | https://github.com/EricsonWillians/BiasedDoom | READ (README scope) |
| SRC-04 | Official upstream repo/readme | https://github.com/chocolate-doom/chocolate-doom | READ (README scope) |
| SRC-05 | User's project repo/README and AGENTS | https://github.com/GhostMan612/Sovereign-Nodes | READ (selected files) |
| SRC-06 | User's project MAPINFO | https://github.com/GhostMan612/Sovereign-Nodes/blob/main/games/SovereignNodesFPS/game/MAPINFO.txt | READ |
| SRC-07 | User's project GLDEFS | https://github.com/GhostMan612/Sovereign-Nodes/blob/main/games/SovereignNodesFPS/game/GLDEFS.txt | READ |
| SRC-08 | User's project ZScript core | https://github.com/GhostMan612/Sovereign-Nodes/blob/main/games/SovereignNodesFPS/zscript/core.zs | READ (partial source) |
| SRC-09 | User's project handoff script | https://github.com/GhostMan612/Sovereign-Nodes/blob/main/games/SovereignNodesFPS/zscript/sn_handoff.zs | READ (partial source) |
| SRC-10 | User's project SESSION_HANDOFF | https://github.com/GhostMan612/Sovereign-Nodes/blob/main/SESSION_HANDOFF.md | READ (partial historical notes) |
| SRC-11 | Windows Chocolate Doom legacy build guide | https://www.chocolate-doom.org/wiki/index.php/Building_Chocolate_Doom_on_Windows | REFERENCED, verify freshness |

## Evidence quality definitions

- **READ:** text reviewed at retrieval time; no guarantee file still matches later branch HEAD.
- **PINNED:** SHA, raw file path, retrieval date recorded; no current source PINNED yet.
- **EXECUTED:** exact local test reproduced with logs; none.
- **PASS:** satisfied explicitly scoped verification criterion; none.

Before promoting a claim from README to architecture fact, inspect pinned implementation and reproduce relevant tests.
