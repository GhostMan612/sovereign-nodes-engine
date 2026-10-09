# WO-000D — First-pass review and independent-review queue

**Author review status:** DOCUMENTATION REVIEW PERFORMED; independent review **NOT DONE**.

## Correctness checks in authored packet

1. Distinguishes source-derived engine CMake facts from README claims and unknown installed host versions.
2. Separates Windows MSVC/CMake generator lanes, the UZDoom optional updater MSVC restriction and required build Python interpreter from gameplay Python support.
3. Separates BiasedDoom GLTF and embedded-Python configurations; no assumption the latter is sandboxed.
4. Defines frame-time metrics including 1%-low estimation, p95/p99 and repeated measurements; does not invent FPS.
5. Requires C-001…C-008 custom Sovereign Nodes game parity before benchmark acceptance; carries WO-C sprite/handoff issues forward.
6. Keeps proprietary IWAD and private genealogy out of ZIP, source repo and public logs.

## Independent reviewer challenges

- Check pinned source paths and line numbers against full file, not solely an extracted excerpt.
- Validate commands against target CMake options and any required bundled resource targets, toolchain and compiler version; commands are prototypes only.
- Determine whether build benchmark methodology measures the same rendering work; detect hidden VSync, model/light differences, shader cache, thermal drift.
- Review current dependency CVEs, licensing of all built-in resources and transport/installer security.
- Ask whether source-game `hasParadox` and sprite naming bugs warrant a **game-copy repair** in a separately authorized effort before deciding engine.

## Disposition

Author review does not approve technical G4/G5 or Phase 00 foundation ADR. All independent findings and operator signoff pending.
