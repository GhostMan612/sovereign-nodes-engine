# WO-E — Evidence gap matrix and owners

| Gate | Available research artifact | Missing decisive proof | Suggested next evidence record | Role |
|---|---|---|---|---|
| G1 Source | WO-A/B/C/D pinned Git source files | independent spot check, fresh candidate refs at test start | `SNE-000E-REVIEW-RECORD.json` | independent reviewer |
| G2 Rights | `DEPENDENCY-LICENSE-MATRIX.md` | transitive SBOM, bundled notices, assets, proprietary IWAD rights | WO-D dependency record and asset notice list | legal/license reviewer |
| G3 Parity | WO-C 15-case test catalog | game executable output C-001…C-008 by candidate | WO-E compatibility proof template | device operator |
| G4 Build | WO-D command and CMake matrix | installed compiler/SDK, controlled compilation, hash evidence | WO-D build + hardware templates | device operator |
| G5 Performance | WO-D run plan and lighting profiles | three controlled UHD 620 traces, p95/p99/1% low | WO-D run template and raw trace hash | device operator |
| G6 Security | WO-C handoff and WO-D threat checklist | corrupt/stale boolean/replay, Python isolation and Mantle threat review | signed tester + reviewer notes | security reviewer |
| G7 Independence | WO-C/D author findings and this WO-E audit | third party source/error review and dissent resolution | WO-E independent review template | independent reviewer |
| G8 ADR | conditional recommendation and alternatives | operator-approved engine, accepted risks and rollback | operator ADR form | operator |

## First critical probes

1. Sprite identity and GLDEFS attachments on the exact packed project, not an invented sprites-only demo.
2. `hasParadox` JSON boolean truth table with schema/missing/stale controls and no sensitive data.
3. GZDoom/UZDoom custom MAP01 marker plus ZScript HUD actor chain.
4. Same-source game content, dependency and build configurations for comparison; no vendor logo/art packaging assumptions.
5. Actual UHD 620 performance and thermals only after parity.

**Every row still contains a missing proof.** No honest ADR can be adopted on this matrix alone.
