# SNE-WO-000B — Downstream maintenance and fork-risk assessment

**Qualitative assessment:** Research-derived architectural judgment. No numeric score or empirical merge-conflict data has been collected.

| Option | Benefits | Recurring obligations | Current uncertainty |
|---|---|---|---|
| GZDoom fork | Compatibility with existing target, mature ZScript/voxels/GLDEFS, C++17 baseline | Cherry-pick security fixes, retain upstream notices, maintain fork CI | Release/patch cadence, code merge effort, high-end feature pressure |
| UZDoom fork | Community continuation, C++20, familiar actor/render APIs | C++20 build toolchain, differences from original GZDoom, AI-authored work cannot be sent as upstream PR | Current game parity, support for target laptop, contribution ecosystem alignment |
| BiasedDoom fork | Modern glTF feature already implemented and opt-in Python stack | Experimental feature interactions, multiple optional dependency paths, C++17 but larger renderer scope | glTF test results, embedded texture path, Python security, ZScript roadmap |
| Original bespoke engine | Full API control, no upstream merge conflicts | Every VM, loader, collision, actor, map, asset and rendering capability self-maintained | 2–5+ year ambition; not selected for immediate parity goal |

## Fork delta discipline

1. Preserve original engine source directory structure until first build passes.
2. Keep an `UPSTREAM.md` with exact pinned upstream commit, remote URL, branch strategy, and locally applied patches.
3. Isolate each enhancement under a feature flag and a separate commit.
4. Require reproduction of Tier-A gameplay before every major merge.
5. Keep engine code and copyrighted third-party/game assets in separate packaging sets.
6. Never promise to upstream AI-assisted patches to UZDoom in violation of its contributor rules.
7. Record maintenance debt before replacing inherited renderer or serializer.

## Required evidence to select foundation

At least two candidate engines must be built and launched with the same synthetic Sovereign Nodes FPS package on the target Dell, or the ADR must explicitly document why the second candidate could not be evaluated. Capture reproducible source/toolchain identity, Tier-A matrix, frame-time stress suite, license clearance, and operator acceptance.
