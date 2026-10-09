# SNE-VER-000D — Packaging validation and unexecuted runtime gates

## Package-generation gates

| Gate | Required | Scope |
|---|---|---|
| V1 | ZIP central directory/CRC test | all  archive entries |
| V2 | exact archive paths, no duplicate/casefold collisions or traversal | all entries |
| V3 | UTF-8, LF line endings, terminal newline, no trailing whitespace | Markdown/JSON contents |
| V4 | JSON schemas/examples parse with syntactically valid JSON | all JSON entries |
| V5 | SHA-256 ledger matches member bytes, excluding its own self-referential hash | every other member |
| V6 | all declared REPLACE preimage Git blob hashes match source at baseline | explicit exact paths |
| V7 | exact count of additions vs replacements and no scripts/binaries/.git/IWAD | manifest vs ZIP |

## Runtime and platform gates

**NOT RUN:** Windows inventory, actual compiler detection, CMake configure, engine build, engine runtime, source game parity, UHD620 measurements, frame-time QA on real traces, dependency transitive SBOM review, official IWAD provenance review and independent acceptance. The JSON `BUILD-VERIFICATION` report is a package-generation result only, not the engine build result.

## Operator installation

Confirm `git rev-parse HEAD` equals required SHA and repo clean **before extraction**; after merge inspect `git status --short`, `git diff --check`, then stage exactly the listed files and run `git diff --cached --check`. Untracked Markdown is invisible to unstaged check until staged. No push by assistant.
