# SNE-WO-000A — Existing-game source inventory and Tier-A contract

- Phase: `SNE-P00`
- Status: **SOURCE RESEARCH IN PROGRESS — REVIEW PENDING**
- Operator requested continuation: 2026-10-09
- Mode: READ ONLY, curated records; no builds, game launches, engine changes or pushes
- Source pin: `GhostMan612/Sovereign-Nodes@44034e97fd22129f919a18cadceb84466ef1bcd3`

## Mission

Pin the game's revision; inspect FPS and Godot launch/handoff source; enumerate load-bearing maps, actors, scripts, graphics, packaging, and data boundaries; translate observed contracts into Tier-A compatibility tests.

## Completed source-inspection substeps (NOT runtime passes)

- [x] Pin exact game and SNE revision.
- [x] Read existing game README, RULES, MAPINFO, GLDEFS, core/hud/handoff/doomednum files.
- [x] Read map generator, WAD validator, PK3 builder, Godot launcher and handoff producer.
- [x] Identify MAP01–03 and baseline ZScript/GLDEFS/handshake invariants.
- [x] Draft source-linked Tier-A compatibility matrix and initial review risks.

## Still open

- [ ] Review binary map contents and actual generated PK3 assets.
- [ ] Complete all active actor/call-path and cross-runtime dependencies.
- [ ] Independent reviewer validates source excerpts and detects omissions.
- [ ] Operator accepts 000A inventory gate.
- [ ] Runtime/parity testing after separate authorization; never part of read-only source review.

## Deliverables

- `evidence/sources/SNE-SRC-GAME-001.md`
- `blueprints/research/SOVEREIGN-NODES-INVENTORY.md`
- `blueprints/research/SNE-000A-TIER-A-COMPAT.md`
- `artifact-chain/evidence/SNE-EVD-000A.md`
- `artifact-chain/verification/SNE-VER-000A.md`
- `governance/WO-000A-REVIEW-FINDINGS.md`
- `artifact-chain/acceptance/SNE-ACC-000A.md`

## Exit gate

No omitted load-bearing game files; each claim pinned by repo SHA/path; testable Tier-A contract; independent review recorded. **Not yet satisfied.**

## Guardrails

No source modifications, no upstream fork, no build or execution claims, no commercial IWAD, no real personal genealogy, no chat logs, no remote edits. All result states explicit.
