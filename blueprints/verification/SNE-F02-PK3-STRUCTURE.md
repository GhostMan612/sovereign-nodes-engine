# F-02 — Static PK3 inventory and the source packager contract

**No local generated PK3 has been inspected.** Read-only source observation from `https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/tools/build_pk3.py#L380` and `https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/game/MAPINFO.txt#L25`.

## Expected original packager `collect()` output, conditional on files existing

- Archive-root `MAPINFO` and `GLDEFS` (without `.txt` extension).
- The three `zscript/core.zs`, `zscript/sn_handoff.zs`, `zscript/hud.zs` fragments from MAPINFO; optional `zscript/doomednum.txt` if on disk.
- `maps/*.wad` from on-disk project maps and `sprites/*` from actual project sprites; enumerate actual entries and content hashes, not source guesses.
- **Deliberately omit `SNDINFO`** in this pinned packager; source comment says sound alias mapping failed on available non-stock IWAD. Do *not* mark its absence FAIL under this source revision.
- Reject misplaced `game/MAPINFO.txt`, duplicate case-insensitive path, archive traversal, missing root definitions, missing fragments, zero map WADs or wrong byte hashes when truly observed.

## Future static admission cases

| ID | Observation to capture | Source of assertion | Status now |
|---|---|---|---|
| PK3-S01 | Original `SovereignNodes.pk3` exists; SHA, size, raw ZIP integrity and central directory | authorized actual file | UNKNOWN |
| PK3-S02 | `MAPINFO`, `GLDEFS` root entries exist and match *actual input* hashes | builder `collect()` | NOT RUN |
| PK3-S03 | all declared fragment contents and optional doomednum presence are consistent | original MAPINFO + archive names | NOT RUN |
| PK3-S04 | `maps/MAP01.wad`,`MAP02.wad`,`MAP03.wad` present if generated and their actual SHA logged | builder map glob + MAPINFO | NOT RUN |
| PK3-S05 | sprites exact frame names and actor mapping; do not infer visible rendering | actor source + resource names | NOT RUN |
| PK3-S06 | `SNDINFO` intentionally absent under pinned builder; unexpected inclusion separately investigated | pinned source | NOT RUN |

ZIP integrity/structural lint ≠ successful ZScript compile, IWAD compatibility, actual `GapNode`, GLDEFS emission or C-001 PASS. Actual PK3 read needs explicitly approved paths and legal source; no game asset bytes are included in this plan.
