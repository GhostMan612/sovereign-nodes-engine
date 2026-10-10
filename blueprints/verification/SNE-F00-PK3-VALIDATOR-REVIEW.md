# F-00 — Missing validator name and actual packaging checks

## Contradiction requiring resolution

`zscript/core.zs` at `44034e97fd22129f919a18cadceb84466ef1bcd3`, around lines 30–36 and 63–66, references a `tools/validate_pk3.py` as though it exists. A direct GitHub pinned path fetch for `games/SovereignNodesFPS/tools/validate_pk3.py` returned **404 NOT_FOUND** in the author's selected read-only audit. **This is a path-level absence at a pinned revision, not proof that validation is impossible.**

Primary tool paths that **do** resolve at that SHA:

- `https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/tools/build_pk3.py`; blob `547c1f552de2e60373c112d7fd3a8717a72ae4db`. It checks ZScript fragment declarations, source contracts and imports `validate_wads` in relevant packaging paths. Inspect actual dependency/entrypoint and stop conditions; no validator execution has occurred.
- `https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/tools/validate_wads.py`; blob `cff34dc0934568ab7311b9cdc062a92743e78a77`. Its presence says nothing about valid output WADs on the operator's machine.
- `https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/game/MAPINFO.txt`; blob `c26536e370e70376d47c35d9c984ef7db6d0215e`. Its declarations do not prove correct ZIP root placement or game launch.

## Independent reviewer path-resolution protocol

1. List exact directory members in full **pinned Git tree**; check filename case, alternate `tools/` or nested directories, and symlink/submodule status if applicable.
2. Search for the literal reference `validate_pk3.py` and the actual functions that implement validations. Distinguish comments, imports, invocation, CLI instructions and true standalone file.
3. Open `build_pk3.py` and identify exact built-in checks, `validate_wads` integration and whether a separate validator is ever imported, invoked or required.
4. If stale documentation: record a proposed comment correction under a **separate authorized source-game work order**. Do not create a fake validator in this docs package.
5. If functionality is absent: record a `NOT IMPLEMENTED/NOT RUN` check and develop a testable proposal; don't mark C-008 PASS or engine regression.

## False-positive controls

- A comment announcing a tool is not proof the file exists.
- `build_pk3.py` having a check function is not proof that it ran, or that the engine loaded the custom MAP01 rather than IWAD Entryway.
- Header byte `dirofs=12` may be a generator constraint; do not treat it as a universal WAD requirement.
