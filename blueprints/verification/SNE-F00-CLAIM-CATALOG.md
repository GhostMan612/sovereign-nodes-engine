# F-00 — Prioritized source-claim catalog and traceability

**Author-selected source recheck as of 2026-10-09; external independent verification PENDING.** This catalog is not a new game test, complete game inventory or official licensing decision.

| Claim ID | Priority | Source assertion to verify | Immutable source path | Gate | Source state |
|---|---|---|---|---|---|
| F00-C01 | P0 | MAPINFO `version "4.14"` precedes three ZScript `addfragments` | `https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/game/MAPINFO.txt#L25-L29` | G1/G3 | SOURCE-OBSERVED |
| F00-C02 | P0 | MAP01 GapNode, MAP02 Breach, MAP03 Warren definitions exist | `https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/game/MAPINFO.txt#L36-L56` | G1/G3 | SOURCE-OBSERVED |
| F00-C03 | P0 | `core.zs` declares ORESHAA0 and TOOLAA0 frame constants | `https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/zscript/core.zs#L63-L74` | G1/G3 | SOURCE-OBSERVED |
| F00-C04 | P0 | GLDEFS includes those texture strings and pointlight associations | `https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/game/GLDEFS.txt#L21-L59` | G1/G3 | SOURCE-OBSERVED |
| F00-C05 | P0 | GZDoom sprite loader documents four-character family/frame/rotation | `https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/src/r_data/sprites.cpp#L297-L323` | G1/G3 | SOURCE-OBSERVED |
| F00-C06 | P0 | Godot serializes `hasParadox` as a JSON boolean | `https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodes/src/world/fps_launcher.gd#L190-L210` | G1/G6 | SOURCE-OBSERVED |
| F00-C07 | P0 | ZScript reads paradox value through `ScanInt`, then nonzero conversion | `https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/zscript/sn_handoff.zs#L178-L207` | G1/G6 | SOURCE-OBSERVED |
| F00-C08 | P0 | Hand-off accepts missing/newer schema with warnings and continues parsing | `https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/zscript/sn_handoff.zs#L158-L183` | G1/G6 | SOURCE-OBSERVED |
| F00-C09 | P0 | `validate_pk3.py` is referenced, but exact pinned path direct fetch returned NOT FOUND | `https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/zscript/core.zs#L30-L36` | G1/G3 | DISCREPANCY/OPEN |
| F00-C10 | P0 | `build_pk3.py` checks fragment references and calls `validate_wads` | `https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/tools/build_pk3.py#L60-L91` | G1/G3 | SOURCE-OBSERVED |
| F00-C11 | P0 | Engine foundation selection and P00 technical gates remain open | SNE ADR and `governance/PHASE-00-REVIEW-GATES.md` at `1c01d2ff5bc3a1369210a7d68dd58269ecf6506d` | G7/G8 | DOCUMENT-OBSERVED |
| F00-C12 | P1 | GZDoom root CMake C++17; Windows vcpkg static target conditional | `https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/CMakeLists.txt#L1-L50` | G1/G4 | SOURCE-OBSERVED |
| F00-C13 | P1 | UZDoom C++20, LTO option, optional updater, Python build dependency | `https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/CMakeLists.txt#L1-L55` | G1/G4 | SOURCE-OBSERVED |
| F00-C14 | P1 | UZDoom's own contribution guide rejects AI-generated/assisted upstream code submissions | `https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/CONTRIBUTING.md#L90-L131` | G1/G2 | SOURCE-OBSERVED |
| F00-C15 | P1 | BiasedDoom C++17, optional embedded Python and conditional glTF/fastgltf | `https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/CMakeLists.txt#L1-L98` | G1/G4/G6 | SOURCE-OBSERVED |
| F00-C16 | P1 | `validate_wads.py` exists but a successful run has not been recorded | `https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/tools/validate_wads.py` | G1/G3 | SOURCE-OBSERVED/NOT RUN |

## Non-transferability

`SOURCE-OBSERVED` supports what text exists. It does **not** mean the long sprites fail at runtime, `ToInt(true)` returns a known integer, all root resources load, packaging validators PASS, or any candidate builds/renders on UHD 620. Full source-tree and transitive licensing coverage remains an additional task.

## Reviewer policy

All **P0** rows must be checked from primary source by an independent reviewer before G1/G7 signoff. Sample P1 rows by stated risk and include at least one attempted falsification per candidate. If the blob moved, compare exact pinned bytes or explicitly register an alternate revision; do not silently edit historic claims.
