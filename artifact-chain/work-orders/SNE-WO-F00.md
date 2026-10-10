# SNE-WO-F00 — Independent source and evidence review handoff

- Release: **v0.9.0**; Phase: **SNE-P00**; sub-workstream **F-00** of `SNE-WO-000F`.
- Source control base for this proposed overlay: `1c01d2ff5bc3a1369210a7d68dd58269ecf6506d`.
- Historical source game pin: `44034e97fd22129f919a18cadceb84466ef1bcd3`.
- Status: **AUTHOR SOURCE RECHECK COMPLETE FOR SELECTED CLAIMS / EXTERNAL INDEPENDENT REVIEW NOT COMPLETE**.
- Authorized action: creation and operator installation of a Markdown/JSON review packet only. This work order grants **no** local execution, software install, engine build, game launch, benchmark, upstream PR, fork, original-game edit or GitHub mutation.

## Mission

Create an independently executable **read-only source review** packet that a distinct reviewer can use to reproduce primary-source claims and resolve contradictions between the published A–F documents before the operator authorizes any hardware, fixture or engine testing. An author's repeat inspection is *not* independent G7 signoff.

## Entry facts

- Research and verification **documents** A–F published; formal technical acceptance still pending.
- Foundation `ADR-SNE-002` remains **HOLD / NO ENGINE SELECTED**.
- Pinned source exists for MAPINFO, GLDEFS, ZScript, handoff writer, packager, GZDoom sprites, UZDoom contribution requirements, and BiasedDoom CMake feature switches.
- The game contains references to `tools/validate_pk3.py`; direct lookup at the frozen game path returned NOT FOUND. The actual alternate validator implementation must be assessed, not guessed.
- No original PK3 hash, actual Windows toolchain, native binary, frame trace, full SBOM, signed independent reviewer, or lawful IWAD identity was supplied.

## Outputs

1. Stable claim IDs with source commit, blob SHA, path and line-oriented review instructions.
2. Author-observed distinctions vs. unproven runtime or licensing claims.
3. Reviewer sampling plan, falsification tests, issue/dissent ledger and exact G1/G7 gate evidence requirements.
4. Blank structured reviewer, issue and operator-signoff templates; no placeholder PASS values.
5. ZIP/manifest preimage and checksum assertions with complete local install/stage instructions.

## Independent reviewer must produce later

- Reviewer identity or private identifier; qualification; appointment/approval; distinct-from-author declaration.
- Independent primary-source reconstruction of every P0 claim, selected P1 claims and contradictory evidence; exact URL/SHA/path/line.
- Issue disposition `SUPPORTED`, `CORRECTED`, `DISPUTED` or `UNRESOLVED`, with suggested remedy, residual impacts and operator decision.
- **G1/G7 cannot pass from this author's file generation or GitHub inspection.**

## Exit conditions

For **documentation handoff readiness only**: every P0 claim has falsification procedure, source identity and reviewer action; no new source changes or false test results; conflicts and follow-up work routed without overwriting history. Technical gates and formal independent review stay OPEN until signed outside this package.

## Stop/rollback

Wrong Git HEAD, changed preimage, unrelated dirty work, existing ADD path, unsupported source claim, sensitive asset, or attempt to self-approve ⇒ STOP. No `git reset --hard`, `git clean`, force push, `git add .` or network installation. Operator owns explicit staging/commit/push after complete diff review.
