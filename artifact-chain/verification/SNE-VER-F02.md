# SNE-VER-F02 — Documentation overlay validation scope

## Package-generation acceptance

- ZIP central directory and all member CRCs valid; no duplicate casefold paths, ZIP slip, script, executable, IWAD, non-Markdown/JSON content or `.git` members.
- All text UTF-8, LF, final newline, no tab-indentation policy violation (except within code quotation), no trailing whitespace; JSON parsed.
- Content SHA-256 ledger matches every member **except the self-referential hash ledger entry**.
- All six REPLACE preimage Git blob SHA-1 values anchored to exact published SNE `725fded` parent; new paths are *expected* absent (operator additionally verifies local ADD collisions).
- Manifest accounts for complete additions/replacements; PowerShell explicit staging includes exactly those paths; no `git add .`.

## Explicitly NOT VERIFIED

Host OS/compiler inventory, original game/source binary, original lawful IWAD SHA, generated PK3, custom map existence at runtime, ZScript compilation, sprite/GLDEFS/handoff behavior, reversible fixtures, UHD FPS, SBOM rights and independent G7 approval. These are future signed evidence-gated tasks.
