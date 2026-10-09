# SNE-VER-000C — Verification plan and results boundary

## Package checks versus engine checks

| Gate | Method | Result to record |
|---|---|---|
| P-V1 | archive has exactly declared names rooted at `sovereign-nodes-engine/` | package verifier output, not runtime |
| P-V2 | every member Markdown/JSON is UTF-8, no trailing whitespace or tabs at EOL | package verifier output |
| P-V3 | every declared SHA-256 matches ZIP content; checksum JSON excludes itself | package verifier output |
| P-V4 | every REPLACE path has pinned original Git blob SHA and agreed baseline | preimage ledger + operator diff |
| P-V5 | no executables, secret files, IWADs, Git metadata, unexpected additions | archive inspection |
| P-V6 | staged Git diff after extraction includes all add paths and no whitespace errors | **OPERATOR NOT RUN** |
| T-A | game load/ZScript/MAPINFO/sprite/GLDEFS/hand-off/hub | **NOT RUN** |
| T-R | voxel/glTF/lights/fallback performance | **NOT RUN** |
| T-W | transitions/save/load/world-state snapshot | **NOT RUN** |
| T-S | schema, replay, Python and Mantle trust separation | **NOT RUN** |
| T-P | target Dell UHD 620 repeatable frame-time benchmarks | **NOT RUN** |

## Evidence recording rules

A PASS requires command+binary revision, fixture hash, output, exact scenario and reviewer; never infer a PASS from README, source path, package integrity, or absence of a build error. Prepare dedicated operator authorization for any runtime/build/test. No local shell execution by research agent. The original game repo's end-of-plan/manual-build discipline remains binding.

## Handoff

After installation, operator provides `git status --short`, `git diff --check`, `git diff --stat`, then stages explicit paths and shares `git diff --cached --check` and `--stat`. Once verified and operator accepted, commit/push are manual. Formal acceptance independently reviewed.
