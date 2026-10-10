# F-02 — Resolve stale `validate_pk3.py` reference without inventing an artifact

## Source-backed conflict

- At original game revision `44034e97fd22129f919a18cadceb84466ef1bcd3`, `zscript/core.zs` comments mention `tools/validate_pk3.py` (selected line 35) and a sprite validator.
- Direct read-only GitHub lookup for `games/SovereignNodesFPS/tools/validate_pk3.py` at that revision returned `NOT_FOUND` in F-00 research. This is **path absence at selected pin**, not proof no equivalent validator exists.
- **Verified instead:** `games/SovereignNodesFPS/tools/build_pk3.py` defines `check_fragments`, `check_mapinfo_order`, `check_sprites`, `check_tags`, `check_maps`, `check_handoff_contract`, `check_zscript_structure`, and `check_layout_below` before writing PK3.
- `build_pk3.py` imports `validate_wads` and calls its parser for WAD checks; `tools/validate_wads.py` is present. Neither code presence nor self-reported printed success proves a local PASS.

## Independent reviewer resolution sequence

1. Open exact frozen Git tree and the current operator-selected game revision, list all `tools/` entries, capture immutable source/path evidence.
2. Identify whether `validate_pk3.py` was renamed, removed, only documented, or implemented in `build_pk3.py`; don't assume which until reviewed.
3. Map each *claimed* validation capability to actual functions/line ranges; distinguish exact sprite-file existence, parser checks, WAD byte semantics, ZScript compile and actual gameplay.
4. Identify the true packaging entrypoint and expected generated output location; record which checks are skipped, optional or dependent on a tool not yet installed.
5. Issue `DISCREPANCY RESOLVED (SOURCE PATH ONLY)` only when independent reviewer records proof and operator accepts correction; keep runtime gates NOT RUN.

No file renaming, Python run or source-game edit is authorized by the documentation.
