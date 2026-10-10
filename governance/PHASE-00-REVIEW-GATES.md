# SNE-P00 — Gate closure and execution authorization, v1.0.0

Document publication, source verification, test execution, independent acceptance and the foundation decision are **different states**.

| Gate | Required independently reviewable proof | Actual state after F-01 *design* | Block example |
|---|---|---|---|
| G1 | immutable source Git URLs/revisions and verified blob claims; distinct reviewer | AUTHOR RECHECK / INDEPENDENT PENDING | stale blob interpreted as build proof |
| G2 | complete source/dependency/asset license and lawful IWAD rights decisions | NOT CLEARED | unowned WAD/brand repackaged |
| G3 | C-001…C-008 unchanged PK3 on genuine custom GapNode by pinned engine with controls | NOT RUN | vanilla Entryway fallback |
| G4 | recorded Windows/compiler/dependency pin and reproducible executable/resource SHA-256 | NOT RUN | only theoretical CMake commands |
| G5 | >=3 real UHD 620 trace captures per agreed configuration + thresholds | NOT RUN | manufactured FPS, different visuals |
| G6 | synthetic-only handoff parse, missing/stale data and Python/Mantle boundary checks | NOT RUN | real lineage disclosure or execution |
| G7 | reviewer genuinely distinct from author, primary-source audit and documented dissent | NOT COMPLETE | author's own red-team renamed independent |
| G8 | G1–G7 disposition plus scored evidence, rollback and operator-selected engine commit | **HOLD** | preference treated as adoption |

## F-01 categories — none are currently active

| Category | Task boundary | Approval needed before use |
|---|---|---|
| `AUTH-R` | independent read-only source/claim review | reviewer appointment + explicit operator approval |
| `AUTH-H` | non-invasive local metadata inventory | machine/path/data bounds + separate operator approval |
| `AUTH-F` | synthetic fixture creation in disposable workspace | allowed writes/source hash and cleanup bounds |
| `AUTH-B` | native engine configure/build | pinned source, deps, output dirs, network policy and build approval |
| `AUTH-T` | local gameplay/compatibility run | lawful external IWAD, binary/PK3 identity, session and log bounds |
| `AUTH-P` | hardware frame-time benchmark | approved scene/profile/threshold/device and stress stop |
| `AUTH-S` | security/license audit | allowed records and private-data/redaction boundary |
| `AUTH-I` | actual game or engine code implementation | **separate future implementation work order**; not granted here |
| `AUTH-D` | redistribution and upstream contribution | separate rights and policy acceptance; not granted here |

## Evidence and approval semantics

- A proposed JSON form is **not** operator consent. State `PROPOSED`, missing fields, expired time or revoked scope → **NOT AUTHORIZED**. Signed scope must be authenticated by the operator through an accepted private channel before dispatch.
- One permission may never be inherited: `AUTH-H` does not allow `AUTH-F/B/T/P`; `AUTH-R` does not permit local device access; `AUTH-B` does not allow `AUTH-I/D`.
- A reviewer can attest source facts without authorizing commands. The operator chooses and revokes permissions; the tester logs actual evidence; a separate qualified reviewer adjudicates tests.
- Defaults for tests are `NOT RUN`. When blocked by consent, lawful resources or dependencies use `BLOCKED` with reason, never fabricated `FAIL/PASS`.
- An `APPROVED` record must name exact subject, operator evidence reference, task ID, working directory, permitted read/write paths, candidate revisions, tool/network policy, time window, logs, stop/rollback and no data scope creep.
- F-00 independent source audit is still pending; any high-severity claim dispute remains HOLD even if a narrow metadata-review proposal is drafted.

## Safe decision order

Propose request → independent/documentary checks → operator authenticates explicit approval for one category → freeze scope/hash and date → recheck actual current state → execute *only that future approved task* → collect redacted evidence → independent review → operator reconciliation. Revocation stops new steps immediately. No F-01 file itself performs this lifecycle or closes any G1–G8 gate.

See `governance/WO-000F-AUTHORIZATION-MATRIX.md`, `blueprints/verification/SNE-F01-AUTHORIZATION-LIFECYCLE.md`, `templates/SNE-F01-AUTHORIZATION.json` and `blueprints/decisions/ADR-SNE-002-FOUNDATION-PENDING.md`.
