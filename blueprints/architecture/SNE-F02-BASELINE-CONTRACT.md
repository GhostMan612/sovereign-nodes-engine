# F-02 — Baseline identity and truth boundary

## Inputs and invariants

- Planning SHA `725fded39c0d50139ab76182211e32375bc2764e` describes *documentation*. Game source SHA `44034e97fd22129f919a18cadceb84466ef1bcd3` describes *text*, not a compiled/packaged PK3.
- Original B0 PK3 is identified only after its SHA-256, exact internal entries and builder inputs are independently captured. Do not invent a B0 checksum.
- Lawfully accessed IWAD stays outside the repo and ZIP; private rights evidence and path recorded off-repo, only redacted reference/hash in publication.
- B1 sprite changes and B2 synthetic handoff data live in explicitly approved isolated workspaces. Every mutation has single-variable manifest, input/output hash and expected counterexample.
- `Map title == GapNode` is insufficient for runtime parity without *unique geometry/actor plus PK3 negative control*. Static MAPINFO existence is not proof of runtime load.
- The original game's tool `build_pk3.py` selects root `MAPINFO`, `GLDEFS`, fragments, `zscript/doomednum.txt` if present, `maps/*.wad`, `sprites/*`; source comments and collect() **deliberately omit SNDINFO** at pinned revision.

## Evidence flow (future)

`Author-reviewed source` → `operator AUTH-H/R` → `device identity (redacted)` + `B0 source/package/rights hashes` → `operator AUTH-F` → `B1 sprite / B2 handoff fixture diff` → **separate** `AUTH-T` → `real candidate runtime proof` → `independent review` → `operator gate reconciliation`.

No arrow grants permission to the next. No modified fixture can upgrade unchanged B0 failure to PASS. ZDaemon belongs to a separate native multiplayer lane; GZDoom/UZDoom tests cannot certify its support.

## Interfaces

Input: F-01 scope JSON plus private authenticated consent; outputs: `templates/SNE-F02-*.json` with `NOT RUN`/`UNKNOWN`, then future separately authored executed records. Published files contain only immutable public source pointers and redacted summaries.
