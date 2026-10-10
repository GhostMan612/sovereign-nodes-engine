# F-00 — Author source-review findings (NOT independent)

| Finding ID | Author observation | Confidence/limitation | Reviewer challenge |
|---|---|---|---|
| AF-01 | Game MAPINFO 4.14, fragments and three named maps exist | HIGH for source; runtime NOT RUN | confirm grammar and actual PK3 placement independently |
| AF-02 | Long frame strings `ORESHAA0` and `TOOLAA0` coexist with four-character GZDoom sprite-family parsing | HIGH for text, MEDIUM for risk | trace aliases/texture lookup rather than assuming failure |
| AF-03 | Godot writes boolean; ZScript `ScanInt` attempts numeric conversion | HIGH source shape mismatch, result UNKNOWN | inspect ToInt semantics and default state |
| AF-04 | ZScript warns on absent/newer schema and proceeds | HIGH selected path, safety implications UNTESTED | trace every return/caller and malformed input |
| AF-05 | `validate_pk3.py` referenced in game comments, direct pinned path fetch failed | HIGH for failed lookup, unknown alternate location | independent full-tree inspection and actual validator entrypoint |
| AF-06 | `build_pk3.py` and `validate_wads.py` exist at pinned revision | HIGH for path, no execution | inspect algorithm and real coverage |
| AF-07 | GZDoom C++17, UZDoom C++20, BiasedDoom C++17 root options | HIGH source, no build evidence | inspect transitive dependency/platform targets |
| AF-08 | UZDoom upstream rejects AI-assisted code PRs | HIGH source policy, no legal clearance | distinguish GPL downstream rights and trademarks |

**Reviewer has not been appointed; no independent approval, P00-G1 final signoff, or P00-G7 signoff is claimed.** The purpose is to give a reviewer falsifiable work rather than a pre-signed conclusion.

## Author corrections and scope cautions

- If a source comment labels a sprite pattern as known good, that is **not** proof the engine loader treats it as valid.
- A `NOT_FOUND` exact path does not prove absence of any equivalent validation code.
- A source-defined glTF option does not prove a working model at runtime.
- Git publication of WO-000F is recorded; WO-F's historic v0.8.0 manuscript still describes an earlier “prepared” state. This v0.9.0 review corrects forward status without rewriting the old commit.
