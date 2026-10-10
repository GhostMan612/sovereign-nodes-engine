# F-02 — Author source-based architecture and quality findings (NOT independent)

## Newly emphasized issue

`build_pk3.py` currently **omits SNDINFO intentionally**. It adds `MAPINFO`, `GLDEFS`, canonical referenced `zscript` fragments and generated maps/sprites at appropriate package paths; its comment explicitly connects this decision to an earlier invalid sound-alias/IWAD failure. Source proof is pinned at `https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/tools/build_pk3.py#L380`. This is not evidence the PK3 successfully builds or works in a running engine.

## Carried high-priority unresolved risks

1. Correct use of unusual ore/locator sprite names in ZScript and GLDEFS versus texture/sprite loaders is not runtime verified.
2. Godot emits JSON boolean; ZScript calls an integer parser. `ToInt` behavior is unverified in the actual engine; true and false controls required.
3. `validate_pk3.py` exact frozen path lookup failed. `build_pk3.py` contains numerous structural validators and imports `validate_wads.py`, but independent full-tree discrepancy review still required.
4. The original generated B0 PK3 bytes, Windows toolchain, legal IWAD identity, GPU renderer and all runtime cases have not been provided.
5. G1 author research and P00-G7 independent reviewer acceptance are distinct; no independent reviewer has been appointed in source records.

## State and limits

F-02 is **a documentation blueprint only**. No native commands executed on operator PC, no fixture generated, no resource downloaded, no source game or engine changed, no gameplay/benchmark recorded and no permissions granted. Archive integrity proves *document bytes only*. Operator must inspect local diff and explicitly stage/push if desired.
