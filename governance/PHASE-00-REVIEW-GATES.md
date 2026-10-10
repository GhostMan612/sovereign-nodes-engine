# PHASE-00 — Independent acceptance and technical decision gates

The package author may self-audit but cannot serve as the independent reviewer or operator. Git publication proves only that bytes reached source control. A reviewer may accept document quality while technical gates remain open.

| Gate | Mandatory observation | Current WO-000E planning state | Hard failure example |
|---|---|---|---|
| P00-G1 Provenance | immutable engine/game URLs, exact SHAs, per-file or symbol claims independently inspected | SOURCE-OBSERVED; independent recheck pending | stale pin, README treated as binary proof |
| P00-G2 Legal/asset | full per-component SBOM, bundled textures/branding/PK3 and lawful IWAD provenance, release terms | NOT CLEARED | unowned commercial data redistributed |
| P00-G3 Tier-A parity | C-001…C-008 on actual game, exact source/binary/PK3 and negative controls | NOT RUN | Entryway accepted as GapNode |
| P00-G4 Build | Windows x64 CMake/SDK/compiler/dependencies, build flags, binary/resource hashes; reproducible trial | NOT RUN | unpinned dependencies or shared CMake cache |
| P00-G5 Device performance | on-device UHD 620 P0, accepted operator thresholds, ≥3 warm traces/scenario, p95/p99/1% low | NOT RUN | FPS invented or from other GPU |
| P00-G6 Security | synthetic-only game handoff, corrupt/stale/schema checks, no private Mantle data; Python opt-in sandbox truth | NOT TESTED | untrusted embedded CPython executes |
| P00-G7 Independence | reviewer other than author; source/error checks and dissent, operator resolves | NOT COMPLETED | author signs own approval |
| P00-G8 Decision | conditional alternatives evaluated; selected commit, risks, exclusion, rollback and operator signoff | **HOLD** | picking engine on features or taste alone |

## Required evidence semantics

`SOURCE-OBSERVED` means a named file/body was inspected; `DOC-CLAIM` means documented upstream behavior only; `TEST-SPECIFIED` is an executable plan only; `NOT RUN` means no build/game/device evidence; `PASS/FAIL` require attached real run and reviewer audit. Use `UNVERIFIED` for uncertain behavior. Never describe unexecuted tests as 'passed'.

## Gate closure flow

1. Independent reviewer completes `templates/SNE-000E-REVIEW-RECORD.json` outside the repository if containing sensitive or internal data; curated sanitized findings may enter governance.
2. Operator verifies every claimed PASS by evidence pointer and reruns high-risk controls if necessary.
3. Operator documents exact approval scope, unresolved waivers and risks; **G2, G3 core blockers, G6 critical security and G7 cannot be silently waived**.
4. Sign updated ADR only after G1–G8 evidence. Separate Phase 01 authorization remains required even if Phase 00 accepted.

Related: `governance/WO-000E-INDEPENDENT-REVIEW-PROTOCOL.md`, `governance/WO-000E-DECISION-CONDITIONS.md` and `artifact-chain/acceptance/SNE-ACC-000E.md`.
