# PHASE-00 — Evidence-gated engine foundation, F-03 build readiness

- Latest operator-published documentation: **F-02 `f2f2cfec676b9a5254fa2a5a7e6f08198581fa09`**. F-03 v1.2.0 is a proposed overlay until manually installed/committed.
- `ADR-SNE-002`: **HOLD / NO ENGINE SELECTED**. Independent F-00 review and G1–G7 acceptance missing; Phase 01 implementation NOT AUTHORIZED.
- **No engine build, host inventory, original PK3 hash, real compatibility test or UHD 620 trace is reported as performed.**

## Published document chain

| Work order | Verified checkpoint | Status |
|---|---|---|
| WO-A | `369722f` | selected source research published, acceptance open |
| WO-B | `edc274f` | engine audit published, acceptance open |
| WO-C | `706db57` | gameplay/renderer test plan published, no runtime |
| WO-D | `1f21e4c` | toolchain/benchmark plan published, no builds |
| WO-E | `1644fb8` | author red-team, ADR HOLD |
| WO-F | `1c01d2f` | evidence readiness only |
| F-00 | `148dc28` | author source-review packet; external reviewer pending |
| F-01 | `725fded` | permissions/scope templates; all unsigned |
| **F-02** | **`f2f2cfe`** | baseline/fixture blueprints, not run |
| **F-03** | **v1.2.0 proposed** | native Windows build readiness only |

## Product / correctness baseline

Existing game requires `MAPINFO version "4.14"`, three ZScript `addfragments`, MAP01 GapNode→MAP02 Breach→MAP03 Warren, sprites/GLDEFS, HUD and Godot→Doom handoff. Historic source game `44034e97fd22129f919a18cadceb84466ef1bcd3`. Control hypothesis GZDoom `c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7`, production comparator UZDoom `dbedcc894fb6866c48520cf27ae773f9957024b9`, experimental BiasedDoom `6147e0670458e48e63d1a40750f36dfc68b00f7f`—none chosen or known to build on target hardware.

## Execution and evidence dependency ordering

1. F-00 independent reviewer checks P0 source claims, particularly validator path, sprite names and boolean parser.
2. F-01 authentic separate scopes for AUTH-R/H/F/B/T/P/S/I/D; all default denied.
3. F-02A actual Windows inventory and B0 PK3/IWAD hashes require scoped AUTH-H; F-02B disposable sprite/boolean fixtures require AUTH-F; engine launch needs separate AUTH-T.
4. **F-03:** actual compiler/build may only follow host/dependency admission and signed separate AUTH-B per candidate. This v1.2.0 release merely specifies commands, source pins, failure oracles and two-trial reproducibility requirements.
5. F-04 requires actual candidate binary/resource SHA, unchanged B0 and lawful IWAD, unique custom GapNode proof with a distinct AUTH-T; F-05 UHD 620 measured frame times require AUTH-P and prior parity.
6. F-06 independent license/security/SBOM review; F-07 independent gate reconciliation and operator ADR G8 decision. `AUTH-I` and `AUTH-D` remain separate regardless of results.

## Non-negotiable

No private Mantle data, commercial IWAD in repo, native test without permission, source-game mutation, engine fork, hidden dependency download, AI-assisted upstream UZDoom PR, fake G4/G5 figures or self-signed independent G7. GZDoom-first means **test control order only**. No action automatically follows Git publication.
