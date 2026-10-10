# WO-E evidence gap matrix — cross-referenced for WO-F readiness

This is a maintained synthesis originally authored in WO-E and updated by WO-F. **No gap has been closed by authoring a plan.** Requirements below point to a future operator-controlled task, not to automatic permission.

| Gate | Existing blueprint | Missing decisive proof | WO-F readiness work | Responsible role |
|---|---|---|---|---|
| G1 provenance | WO-A–E source pins, claim audit | external reviewer spot-check and current SHA crosswalk | `SNE-000F-BASELINE-IDENTITY.md`, `SNE-000F-SOURCE-SNAPSHOT.md` | independent reviewer |
| G2 rights | dependency/license matrix | transitive SBOM, game-data and bundled asset rights | `SNE-000F-MAINTENANCE-LEGAL.md` | qualified rights reviewer |
| G3 parity | 15-case WO-C catalog | per-candidate C-001…C-008 run results, negative controls | `SNE-000F-CASE-TO-GATE-TRACE.md`, `SNE-000F-PK3-AND-WAD-GATES.md` | authorized operator/tester |
| G4 build | WO-D CMake/build prototypes | Windows compiler/SDK/configure/build binary and resource hashes | `SNE-000F-BUILD-ENTRY-GATE.md` | operator |
| G5 performance | WO-D measurement SOP | UHD 620 real comparable frame traces and approved thresholds | `SNE-000F-HARDWARE-TRIAL-MATRIX.md` | operator |
| G6 security | WO-C handoff analysis and Python warnings | true/false, schema, stale, path, replay, sensitive-data negative tests | `SNE-000F-HANDOFF-TESTS.md` | tester + security reviewer |
| G7 independence | WO-E reviewer handoff | independent, documented dissent and resolution | `SNE-000F-REVIEW-ROLES.md` | reviewer separate from author |
| G8 decision | ADR-SNE-002 HOLD, scorecard unscored | completed G1–G7 plus signed operator selection/rollback | `SNE-000F-ADMISSION-CHECKLIST.md` | operator |

## Priority blockers to resolve before attributing failures to any engine

- `F-D01`: sprite frame strings `ORESHAA0` and `TOOLAA0` require actual frame/GLDEFS runtime discrimination against archive alias behavior; source alone does not prove failure.
- `F-D02`: Godot `hasParadox` JSON booleans versus Doom `ScanInt` requires a synthetic true/false truth table; source alone does not prove observed output.
- `F-D03`: `tools/validate_pk3.py` is referenced in pinned game source commentary, yet lookup of that path at pinned game revision did not find a file. Reviewer must locate actual check or classify stale documentation.
- `F-D04`: no candidate can be credited with speed if custom MAP01 is not positively identified as GapNode with unique proof.

All engine builds, gameplay tests, hardware tests, licenses and independent review remain `NOT RUN` or `OPEN` until independent primary evidence exists.
