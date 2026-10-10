# PHASE-00 — Source and execution evidence gates

- Phase ID: `SNE-P00`; documentation release under preparation: **F-01 v1.0.0**.
- Latest operator-published checkpoint observed: **F-00 `148dc28`**; published means committed to Git, not independently accepted.
- Technical phase state: **OPEN**. ADR-SNE-002: **HOLD / FOUNDATION UNDECIDED**. Phase 01 implementation: **NOT AUTHORIZED**.
- Present document is the *F-01 operator authorization and scope-freeze design*, not an operator signature or permission to execute.

## Purpose

Retain the existing Sovereign Nodes game contract — `MAPINFO version "4.14"`, three `addfragments`, actor sprites/GLDEFS, synthetic Godot handoff, MAP01 GapNode → MAP02 Breach → MAP03 Warren — while collecting actual evidence before choosing a Doom-derived engine. Primary reported low-end target: Dell Latitude 5400 i5-8365U, 16 GiB RAM, Intel UHD 620. Host capabilities and measured FPS are still unknown.

## Publication milestones and actual acceptance

| Work order | Commit | Documentation publication | Formal/technical acceptance |
|---|---|---|---|
| WO-000A | `369722f` | PUBLISHED | PENDING |
| WO-000B | `edc274f` | PUBLISHED | PENDING |
| WO-000C | `706db57` | PUBLISHED | C-series NOT RUN |
| WO-000D | `1f21e4c` | PUBLISHED | Windows/UHD NOT RUN |
| WO-000E | `1644fb8` | PUBLISHED | source red-team author only; G7 PENDING |
| WO-000F | `1c01d2f` | PUBLISHED | verification blueprint; execution NOT AUTHORIZED |
| F-00 | `148dc28` | PUBLISHED | external independent review NOT SIGNED |
| **F-01** | PENDING operator commit | **v1.0.0 overlay** | authority form BLANK; all execution NOT AUTHORIZED |

## Ordered evidence program (future and individually controlled)

1. F-00: a *distinct* source reviewer inspects P0 claim texts/line pins, disputes, and `validate_pk3.py` path. Author's review does not complete P00-G7.
2. **F-01: operator chooses exact scope(s), actors, repository revisions, read/write path allowlists, method, network, asset rights, bounded time, abort and evidence storage.** Every request defaults to `PROPOSED / NOT APPROVED`. A signed private authorization is required to promote a request.
3. F-02A host/source inventory can proceed only after `AUTH-H` approval; F-02B synthetic disposable fixtures only after `AUTH-F` plus any needed `AUTH-T`. Metadata review never implies game launch.
4. F-03 native build only after a separate `AUTH-B` approval and dependency/license prerequisites; builds occur outside this planning repo.
5. F-04 compatibility C-001–C-008 with identical unchanged PK3, lawful IWAD and per-engine binary hashes after `AUTH-T`; engine fallback to vanilla Entryway cannot count as PASS.
6. F-05 only after parity and explicit `AUTH-P`: real UHD 620 frame-time traces, controlled VSync/driver/thermals and declared pass thresholds.
7. F-06 rights, security and maintenance under `AUTH-S` with no public proprietary assets; F-07 independent gate reconciliation and a future operator decision.

## P00 acceptance gates

G1 primary-source revision provenance; G2 licenses/asset rights; G3 actual game parity; G4 native Windows reproducible build; G5 actual UHD 620 benchmark; G6 safe synthetic-only handoff/embedded-Python boundaries; G7 independently performed source/results review; G8 operator-signed foundation ADR and rollback. None is closed by F-01.

## Immutable authority boundary

Neither reading, extracting, staging, committing nor pushing an authorization *template* approves an experiment. No game or engine clone/build, host tool installation, game launch, synthetic fixture execution, GPU load, source modification, release, upstream PR or private Mantle access is authorized by this package. Even if a template is marked `APPROVED`, the executing agent must independently verify a specific genuine operator approval, scope, date, expiry and non-revocation; text alone is not an authentication mechanism.

**Next legitimate milestone:** operator selects a narrow review or inventory category and separately approves a concrete work order; record actual evidence before opening another execution step. Keep `ADR-SNE-002` on HOLD.
