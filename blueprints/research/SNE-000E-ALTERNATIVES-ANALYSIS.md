# WO-E — Alternatives analysis and falsification tests

| Option | Most credible benefit | Biggest unresolved counterargument | Falsifying experiment | Current disposition |
|---|---|---|---|---|
| GZDoom `c26ce2e6ca2a` | close inherited semantics of existing 4.14 game, voxels, GLDEFS, hub state | actual script/asset behavior, UHD 620 graphics and future model maintenance | C-001–C-008 + native baseline + P0 traces | CONTROL-LANE HYPOTHESIS |
| UZDoom `dbedcc894fb6` | inherited systems plus actively different code/dependencies | C++20/environment burden, upstream no-AI PR policy, third-party resource licenses | independent Windows build + same C-series + maintenance rehearsal | COMPARATOR |
| BiasedDoom `6147e0670458` | conditional glTF, skeletal animation, PBR/postFX and procedural ideas | ZScript roadmap, GLB textures, unsandboxed CPython, dependency complexity and GPU limits | GLTF ON/PYTHON OFF + Tier-A + texture/animation + 720p trace | EXPERIMENTAL REFERENCE |
| Vanilla/Chocolate Doom | minimal reference behavior, historical code clarity | cannot directly preserve modern script and render pipeline | full compatibility cost study if production proposal arises | EXCLUDE FROM FIRST PRODUCTION TEST |
| Bespoke engine | architectural control | high rewrite risk and costly existing PK3/ZScript compatibility | formal total-cost/risk charter, proof existing forks fail | DEFER |

## Consequence of no selection

NO SELECTION is a real valid outcome. Work may continue on isolated fixture validation, policy/legal assessment and optimized game content only in a **separately authorized work order**. Documentation acceptance does not transfer runtime authority.

## Red-team falsification

Ask reviewers to devise one non-obvious circumstance in which the preliminary GZDoom-first control recommendation is wrong—for example source-game compatibility defects masked by stock-map fallback or a different proprietary data license situation. All candidates must face the same core oracle; the scorecard must not reward simply skipping unsupported features.
