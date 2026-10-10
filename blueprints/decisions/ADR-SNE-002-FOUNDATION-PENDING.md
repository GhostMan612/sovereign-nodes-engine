# ADR-SNE-002 — Sovereign Nodes Engine foundation decision (PENDING)

| Field | State |
|---|---|
| Decision owner | Operator |
| Last document review | 2026-10-09 / WO-000E v0.7.0 |
| Decision | **HOLD / NO FOUNDATION SELECTED** |
| Proposed first verification lane | **GZDoom** — conditional, non-binding |
| Production comparator | **UZDoom** — independently prove compatibility |
| Experimental reference | **BiasedDoom** — glTF/animation/postFX research |
| Independent review | PENDING |
| Windows builds, game launches, UHD 620 runs | **NOT RUN** |
| Legal and release clearance | NOT GRANTED |
| Phase 01 authority | **NOT GRANTED** |

## Decision context

Sovereign Nodes FPS currently uses ZDoom/GZDoom-family `MAPINFO version "4.14"`, three `addfragments`, ZScript actors/HUD/handoff, GLDEFS dynamic lights and MAP01→MAP02→MAP03. The long-term engine seeks voxel actor visuals, optional glTF/skeletal animation, stable low-end GPU behavior, logical world continuity, offline-first control, and synthetic-only protected boundaries for future Mantle interfaces. The initial reference device is Dell Latitude 5400, i5-8365U, 16 GB and Intel UHD 620.

**Source baseline:** engine repository `1f21e4c99da50c83ac0c90d14b2f14a752ae89f4`; existing game `44034e97fd22129f919a18cadceb84466ef1bcd3`. Candidate upstream pins are recorded in `evidence/sources/SNE-000E-FOUNDATION-PIN-LEDGER.md`.

## Alternatives under review

1. **GZDoom:** inherited ZScript, voxel, GLDEFS, hub and renderer seams inspected at pinned revision; lowest-change *hypothesis* for testing today's project. No proof that this pinned build runs the game correctly or fast.
2. **UZDoom:** comparable inherited systems with different C++20/toolchain/LTO/dependency, upstream AI-assisted contribution restrictions, and asset licensing review. Requires a distinct build and runtime lane. Restrictions on upstream PRs are not a blanket GPL downstream fork ban.
3. **BiasedDoom:** modern glTF, lighting and embedded CPython avenues; conditional model compilation, runtime texture limits and non-sandboxed Python make it an experimental *reference* pending robust tests. Its present docs describe ZScript support; future deprecation discussions are not evidence it is absent today.
4. **Chocolate Doom/original Doom:** valuable historical reference; not drop-in modern ZScript plus advanced renderer.
5. **Fresh engine:** highest redesign/compatibility cost; defer unless all fork candidates fail hard gates and operator opens an independent feasibility study.

## Non-binding verification preference

**Start with GZDoom as the control lane**, not the selected foundation. That offers a conservative baseline against which to compare each alternative with the same lawful IWAD, PK3 hash, test steps and hardware conditions. If custom game parity is broken, distinguish pre-existing game defects from engine incompatibility using a fixture-only probe; do not silently patch source game and then declare parity.

## Mandatory evidence before decision

- P00-G1 exact source pins refreshed and provenance independently spot-checked.
- P00-G2 full transitive code and bundled-asset license review, rights and release obligations approved.
- P00-G3 **C-001 through C-008** proven per production candidate on actual project content, with no IWAD fallback and explicit sprite/handoff negative controls; C-009–C-015 triaged with signed risk acceptance if applicable.
- P00-G4 reproducible Windows x64 toolchain, dependencies, resources and build record, with independently reproducible artifact identity; executable provenance and flags retained.
- P00-G5 actual UHD 620 traces under operator-approved thresholds; no score from predictions or a different GPU.
- P00-G6 security review of game handoff, untrusted mods/CPython and separate read-only/synthetic Mantle bridge.
- P00-G7 **person independent of author** reviews source claims, testing, legal evidence and residual risks; dissent retained.
- P00-G8 operator signs explicit alternative comparison, accepted exclusions, rollback and Phase 01 boundary.

## Conditional reject/fallback rules

- Fails C-001…C-008, reproducible startup corruption, or severe crash: **BLOCK candidate**; investigate fixture/game root cause before concluding engine failure.
- Incompatible license or unapproved redistributed assets: **BLOCK distribution/adoption** regardless of FPS.
- Baseline P0 fails operator-agreed frame-time/performance threshold on UHD 620: **BLOCK low-end production lane**, allow research-only if explicitly scoped.
- Model or lighting optional feature fails but baseline parity passes: **downgrade P1–P3**, not unconditional rejection.
- Cannot maintain AI-assisted downstream development legally/practically: **revisit candidate**; never submit AI-assisted code to UZDoom upstream contrary to policy.
- Missing data or independent reviewer: **HOLD**, not lowest-score candidate selection.

## Rollback/contingency

Preserve original game repo, pinned upstream source snapshots, verified official compatibility executable, lawful WAD references and old PK3. Any future fork experiments occur in a separate authorized workspace with no editing the game's source as a side effect. Abort proposed new features by reverting the experimental fork/adapter only; compare C-001…C-008 and save-game semantics again. Do not assume cross-engine save or demo portability.

## Operator decision record (intentionally blank)

- Selected engine, revision and justification: **PENDING**.
- Build evidence IDs and benchmark record IDs: **NONE**.
- Independent reviewer and objections: **PENDING**.
- Licensing sign-off and feature exclusions: **PENDING**.
- Risk acceptance, rollback and execution permissions: **PENDING**.

**This ADR is not an approval to clone, compile, benchmark, modify, fork, redistribute or implement.** See `governance/WO-000E-DECISION-CONDITIONS.md` and `artifact-chain/acceptance/SNE-ACC-000E.md`.
