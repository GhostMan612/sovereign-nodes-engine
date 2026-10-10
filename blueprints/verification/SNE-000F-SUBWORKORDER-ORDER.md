# WO-F — Discrete evidence work orders, dependencies, and authorized execution boundaries

| Sub-ID | Work | Prerequisite | Output | Mandatory distinct approval |
|---|---|---|---|---|
| F-00 | Independent source recheck / missing validator investigation | pinned A–E source | signed review + high-risk corrections | reviewer appointment |
| F-01 | Operator authorization and scope freeze | F-00 findings | one signed authorization JSON per category | operator |
| F-02A | Read-only Windows/game resource inventory | F-01 inventory authorization | environment + source identity | operator metadata approval |
| F-02B | Disposable synthetic sprite/handoff fixture discrimination | F-01 fixture approval | controlled comparison and log hashes | operator fixture/run approval |
| F-03 | Native Windows GZDoom control build and optional separate UZDoom build | complete toolchain/licensing review, F-01 build approval | binary/config/resource fingerprints | operator build approval |
| F-04 | C-001…C-008 actual unchanged game parity | viable binary, lawful IWAD and known PK3 | per-candidate C-series result ledger | operator runtime approval |
| F-05 | UHD 620 P0/optional graphics trials | C-001…C-008 proof and approved thresholds | real raw trace hashes and summaries | operator performance approval |
| F-06 | SBOM, Python threat, asset and fork-maintenance review | source/dependency access; reviewer assigned | signed license/security assessments | rights/security reviewer |
| F-07 | Gate reconciliation + ADR recommendation | complete G1–G7 evidence | HOLD/PASS/FAIL gate ledger, dissent | independent reviewer then operator |

## Parallel versus ordered

- F-00 reviewer appointment and read-only documentation checks may be designed before any device test. Future execution requires operator's separate approval of the permitted read-only sources.
- An approved metadata inventory **does not** grant binary build or game launch rights.
- Legal/license inventory can run in parallel with test planning, but no redistributable binary may be released until clearance.
- P0 gameplay identity and parity come **before** trustworthy benchmarking; optional glTF/light stress comes after P0 stability.
- `ADR-SNE-002` cannot be adopted merely because the final F sub-work-order documentation exists.

## Exit of WO-F overlay

Operator can hand individual sub-work orders to coding/test agents **only after** explicitly selecting and authorizing that category. The current package does not activate any category. No automatic next work order is executed.
