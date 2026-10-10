# SNE-WO-000F — Evidence closure system architecture

## Separation of concerns

| Layer | Owns | Must never own |
|---|---|---|
| Planning repository SNE | work orders, claimed source pins, risk logs, sanitized measurement summaries, independent-review decisions | engine binaries, IWADs, private Mantle graph, uncontrolled test logs |
| Source game `Sovereign-Nodes` | canonical Godot and Doom game content, PK3 generator, map tools and gameplay | experimental engine forks committed implicitly |
| Candidate engine checkouts | future operator-approved native GZ/UZ/BD revisions and isolated build trees | automatic edits to canonical game or planning repo |
| Disposable test workspace | synthetic fixture copies and lawful IWAD *references*; hashes, negative controls | permanent credentials, real-person private export, unchecked generated map writes |
| Raw evidence vault (local) | trace CSV/logs, binary/config fingerprints with secrets scrubbed | public commits containing usernames, paths, game assets or secrets |
| Review/decision | test result adjudication, dissent, scorecard and ADR with operator signoff | self-approved author claims |

## Dependency direction

`Pinned source → authorization → baseline identity → controlled fixture → candidate-specific test → raw evidence hash → sanitized result → independent review → gate decision → signed ADR`.

A compile-ready recipe is not a successful configure; a successful configure is not a completed binary; a binary is not game parity; successful gameplay is not compliant distribution or acceptable performance. No step is automatically promoted when a previous step succeeds.

## First falsification targets

- Source game long sprite families (`ORESHAA0`, `TOOLAA0`) versus engine sprite lookup convention.
- JSON boolean `hasParadox` producer versus Doom integer scanner consumer.
- Game source comments refer to `validate_pk3.py`, but exact pinned path was not fetched; establish validator reality.
- Engine startup may silently use base-IWAD content. Require an unmistakable custom GapNode marker and a missing-PK3 negative control.

## World and bridge boundaries

MAPINFO exits between discrete maps support a *logical* continuity plan, not simultaneous renderer/physics loading. The future Mantle bridge is a synthetic-only, read-only adapter proposal. Untrusted embedded CPython is native-equivalent unsandboxed and must not be enabled by a benchmark fixture.

## Recovery principle

Source game, engine source and user environment must remain untouched by the package. If experiments later alter disposable copies, discard copies to return to hash-verified baselines; do not use destructive Git operations on canonical repos.
