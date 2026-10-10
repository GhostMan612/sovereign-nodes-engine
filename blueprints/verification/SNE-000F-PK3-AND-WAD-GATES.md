# WO-F — Package and WAD identity before engine parity

## Mandatory source and archive distinction

Pinned `game/MAPINFO.txt` begins with `version "4.14"`, declares all three `addfragments`, and maps MAP01 `GapNode` → MAP02 `Breach` → MAP03 `Warren`. `tools/build_pk3.py` exists in the pinned game tree and implements packaging checks; `tools/validate_wads.py` exists and inspects the project's generated map layout. **No author of WO-F built these files or executed the validators.**

### Validator source discrepancy (F-D03)

Game source comments reference `tools/validate_pk3.py` by name. At the pinned Git revision, a direct lookup of `games/SovereignNodesFPS/tools/validate_pk3.py` returned missing, and a repository code search found only the *reference* in source commentary. Do not assume the validator is present/working, and do not count code comments as a passing gate. A reviewer must inspect the actual current repo tree and identify whether `build_pk3.py` provides the relevant checks, the path moved, or the comment is stale.

## Concrete future cases

| Case | Test fixture/oracle | Required controls |
|---|---|---|
| PKG-01 | ZIP/PK3 layout with root `MAPINFO`, `GLDEFS`, declared `zscript/` and all expected `maps/` | no hidden second stale ZScript source path |
| PKG-02 | emitted three WADs parse with exact semantics and playable exits | independent read of directory/lumps, no generator self-certification |
| PKG-03 | engine opens **custom** MAP01 with GapNode title, unique marker and project actor | omit PK3 only in disposable control and prove vanilla Entryway absence/presence |
| PKG-04 | fragment classes instantiate / expected HUD and handoff methods accessible | intentionally absent fragment in disposable package must be detectable |
| PKG-05 | MAP01→MAP02→MAP03 plays with actual switches/exits and map identity | missing-target disposable map cannot count as correct |
| PKG-06 | WAD directory `dirofs` follows **the project's** header-at-12 generator format, not asserted as universal WAD law | generic WADs use their declared directory offset; never force 12 on external WADs |

## Invalidating conditions

Wrong IWAD, missing original PK3 hash, fallback `Entryway`, ZScript load ignored, absent WAD map, inaccurate generator reference, ambiguous map identity or unmet permissions blocks performance scores. Keep official IWADs outside planning repo and ZIP; record only legal provenance and approved hashes.

See WO-C cases C-001–C-008 and the two original tool sources: [build_pk3.py](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/tools/build_pk3.py), [validate_wads.py](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/tools/validate_wads.py).
