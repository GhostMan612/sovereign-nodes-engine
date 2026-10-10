# F-02 — WAD byte/layout and playable-map two-stage oracle

## Stage 1: future static checks, `AUTH-H` or other explicitly approved bounded read

- Identity: original project WAD's byte SHA-256, size, header type (`IWAD`/`PWAD`), lump count, directory offset and full directory bounds; use the file's declared offset.
- Project generator-specific invariant: its first map directory may follow its own header-at-12 layout, but **12 is not a universal WAD directory offset**.
- Validate MAP01–MAP03 references from MAPINFO, map loader lump sequences, THINGS/LINEDEFS/SIDEDEFS/VERTEXES/SECTORS boundaries and structural cross-references.
- Run source-specified `tools/validate_wads.py` only under an approved future command scope; its presence in Git is **not** evidence that it has passed locally.
- Compare an independently specified parser oracle with game generator checks; generator cannot independently certify itself.

## Stage 2: future runtime C-008, separately approved `AUTH-T`

- Launch actual hashed *unchanged* PK3 and lawful IWAD on exact candidate binary.
- Prove unique custom MAP01 geometry/actor and exercise required exits; no stock Entryway fallback, no silent missing MAP02/03.
- Capture startup/parse logs, exact map markers, screenshots and tester outcome, plus disposable negative malformed fixture controls if separately approved (`AUTH-F`).

**State:** both stages `NOT RUN`. Passing a byte parser is only a structural result, never gameplay PASS. No legal IWAD is packaged or redistributable by this document.
