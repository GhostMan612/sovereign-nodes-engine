# Candidate selection matrix — preliminary (not a foundation decision)

**Status:** SEED / NOT ACCEPTED. Research date: 2026-10-09. Feature entries mean *upstream documentation claims* unless marked otherwise.

| Candidate | Source | Compatibility suitability | Modern capability | Key risk | Decision |
|---|---|---|---|---|---|
| UZDoom | https://github.com/UZDoom/UZDoom | GZDoom-family, promising ZScript/advanced-map path | OpenGL/Vulkan, dynamic lighting, 3D floors | maintainers' policies, exact revision/build not checked | SHORTLIST — VERIFY |
| GZDoom | https://github.com/ZDoom/gzdoom | Existing GZDoom-family game target, strong baseline | OpenGL/Vulkan, scripting/modding | maintenance path and exact revision to select | SHORTLIST — VERIFY |
| BiasedDoom | https://github.com/EricsonWillians/BiasedDoom | Claims GZDoom/ACS/ZScript compatibility today | glTF, skeletal animation, expanded lighting, CPython | ZScript deprecation intent, experimental changes, security/perf | EXPERIMENTAL REFERENCE |
| Chocolate Doom | https://github.com/chocolate-doom/chocolate-doom | Vanilla-focused, not a drop-in for modern ZScript | deliberately conservative | extensive rewrite to match current game | STUDY ONLY |
| Original Doom | https://github.com/id-Software/DOOM | excellent historical engine fundamentals | not suitable for modern script/model requirements | portability/compatibility work | STUDY ONLY |

## Weighted decision rubric (fill after research)

| Criterion | Weight | Method |
|---|---:|---|
| Tier-A Sovereign Nodes parity | 30 | Run scripted evidence matrix |
| Fork/merge and build maintainability | 20 | repo dependency/upstream history audit |
| UHD 620 performance baseline | 15 | same-machine repeatable FPS/1% low and frame-time |
| Model, voxel and lighting extensibility | 15 | pinned source implementation review |
| Licensing and maintainer policy fit | 10 | legal notices and contribution policy review |
| World/handoff integration feasibility | 10 | interface and persistence proof |

Score each 0–5 with attached evidence. **No candidate can win if Tier-A parity, license compliance, or minimum-performance gate fails** even when aggregate score is high. Scores remain intentionally blank.

## Source starting points

- UZDoom README and license: https://github.com/UZDoom/UZDoom
- GZDoom README and license: https://github.com/ZDoom/gzdoom
- BiasedDoom README/docs: https://github.com/EricsonWillians/BiasedDoom
- Chocolate Doom README: https://github.com/chocolate-doom/chocolate-doom

## Decision hold

No selected fork or engine package until exact commit pins, detailed source map, verified legal matrix, and local baseline are presented to operator.
