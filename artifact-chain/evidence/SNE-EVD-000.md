# SNE-EVD-000 — Foundation documentary evidence inventory

**Evidence class:** source README/selected repository file content, not executed tests.  
**Collection date:** 2026-10-09. Exact SHA not pinned; refresh before baselining.  
**Confidence:** source contents verified for examined text; behavior unverified.

| Ref | Evidence | URL or path | Supports | Limit |
|---|---|---|---|---|
| SRC-01 | UZDoom README | https://github.com/UZDoom/UZDoom | GZDoom family, advanced renderers, GPLv3+ claimed | no local build |
| SRC-02 | GZDoom README | https://github.com/ZDoom/gzdoom | OpenGL/Vulkan, GPLv3 claimed | no code seam proof |
| SRC-03 | BiasedDoom README | https://github.com/EricsonWillians/BiasedDoom | glTF, CPython, ZScript roadmap claims | implementation untested |
| SRC-04 | Chocolate Doom README | https://github.com/chocolate-doom/chocolate-doom | vanilla philosophy, GPL-2.0 listed | unsuitable inference requires audit |
| SRC-05 | Sovereign Nodes README/AGENTS | https://github.com/GhostMan612/Sovereign-Nodes | split Godot hub and standalone Doom game | SHA pending |
| SRC-06 | Existing MAPINFO source | `games/SovereignNodesFPS/game/MAPINFO.txt` | version 4.14; fragment list; map chain | parse/runtime untested |
| SRC-07 | Existing GLDEFS source | `games/SovereignNodesFPS/game/GLDEFS.txt` | defined attached light data | visuals untested |
| SRC-08 | Existing ZScript source | `games/SovereignNodesFPS/zscript/core.zs` | actor/sprite contracts | compile untested |
| SRC-09 | Existing handoff source | `games/SovereignNodesFPS/zscript/sn_handoff.zs` | handoff schema v1 declared | end-to-end untested |
| SRC-10 | Sovereign Nodes SESSION_HANDOFF | https://github.com/GhostMan612/Sovereign-Nodes/blob/main/SESSION_HANDOFF.md | project-reported historical defects | historical notes aren't tests |

Detailed scope and limitations: `evidence/sources/SOURCE-INDEX.md`.
