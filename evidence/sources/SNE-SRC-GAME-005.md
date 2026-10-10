# SNE-SRC-GAME-005 — Original game high-risk verification handoff

**Repository:** `https://github.com/GhostMan612/Sovereign-Nodes`
**Revision:** `44034e97fd22129f919a18cadceb84466ef1bcd3`
**Inspection:** connected read-only GitHub source file fetches on 2026-10-09.
**Classification:** SOURCE-OBSERVED / TESTS NOT RUN.

## Confirmed contents of selected source files

1. `games/SovereignNodesFPS/game/MAPINFO.txt` (`Git blob SHA-1 c26536e370e70376d47c35d9c984ef7db6d0215e`) begins with `version "4.14"` ahead of `addfragments`; names GapNode, Breach and Warren for MAP01–03.
2. `games/SovereignNodesFPS/game/GLDEFS.txt` (`b98abc8de454617fc5681fb585ac8d41cee71bc9`) declares ELEC/ORESHA/TOOLA and names long texture strings ORESHAA0 and TOOLAA0.
3. `games/SovereignNodesFPS/zscript/core.zs` (`61fb41c797d909404153d77bab894704637ceba4`) defines ore and locator sprite-frame constants containing more than the conventional four-character family plus frame/rotation suffix.
4. `games/SovereignNodesFPS/zscript/sn_handoff.zs` (`c83a8058d602ee6d1c6a7aca2792a5d408db2ebb`) has `KEY_PARADOX`, `ScanInt(text, KEY_PARADOX, paradoxFlag)` and boolean flag derived from integer nonzero comparison.
5. `games/SovereignNodes/src/world/fps_launcher.gd` (`7bbd446af0fb3e9c7f8e2646863101e06fc23f3a`) emits JSON `hasParadox` as Godot `bool(...)`.
6. `games/SovereignNodesFPS/tools/build_pk3.py` (`547c1f552de2e60373c112d7fd3a8717a72ae4db`) contains packaging assertions and text referencing `validate_pk3.py`.
7. `games/SovereignNodesFPS/tools/validate_wads.py` (`cff34dc0934568ab7311b9cdc062a92743e78a77`) is a substantial byte and semantic validator, not an executed result.

## Missing file reference to investigate (F-D03)

Direct `fetch_file` for `games/SovereignNodesFPS/tools/validate_pk3.py` at `44034e97fd22129f919a18cadceb84466ef1bcd3` returned 404; repository code search for filename found a source comment rather than a file. This is a **pinned source/path discrepancy**, not proof that no equivalent validation exists. The local operator/reviewer must check the full tree and canonical packaging entrypoint before asserting such a gate is present or absent.

## Required behavioral proof

- Long sprite/light linkage: `SPR-01..SPR-06` against unchanged original PK3, then single-variable aliases in disposable fixture.
- Boolean handoff: `H-01..H-10` with synthetic true/false; integer-only fixture distinguishes parser behavior.
- Actual custom MAP01: `PKG-01..PKG-06` with a no-PK3 negative control; never equate vanilla Entryway gameplay with successful project boot.
- Cross-candidate comparison: keep original PK3, official IWAD ref, actor/map states, command and exact candidate revision unchanged where possible.

The source record neither authorizes tests nor determines their outcomes. An independent reviewer must recheck every critical source claim against the immutable source body, not only this summary.
