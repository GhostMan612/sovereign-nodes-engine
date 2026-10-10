# WO-F — Operator authorization is granular and revocable

**All default to NOT AUTHORIZED.** Signing a read-only approval does not implicitly permit any subsequent step, even if a planning document contains a command. Use one `templates/SNE-000F-AUTHORIZATION.json` per task category.

| Category ID | Access requested in future | Explicit scope fields | Prohibited without separate approval |
|---|---|---|---|
| AUTH-R | Independent read-only source review | repo URLs/revision, reviewer/date | local device setup or modifications |
| AUTH-H | Host environment inventory | machine, metadata types, redaction/retention | installing components, settings changes, game launch |
| AUTH-F | Disposable fixture preparation | approved sandbox path, synthetic payload, data lifetime | source game edit, IWAD copying to repo |
| AUTH-B | Native source build | exact source SHA, toolchain and build output dir, dependencies/network | unattended installs, repo push, game code patches |
| AUTH-T | Game parity runtime | exact binaries/PK3/IWAD ref/map/fixture, logs, session scope | host OS changes, real Mantle data |
| AUTH-P | Graphics benchmark | approved controller, frames capture/traces, scene, duration, thresholds | unbounded stress, inferred FPS |
| AUTH-S | Security/rights review | allowed sources, review scope, synthetic input | Python arbitrary code execution or private vault |
| AUTH-I | Implementation or upstream contribution | distinct future work order, repo, authority, tests | ANY assumption from WO-F docs |
| AUTH-D | Public redistribution | signed rights audit and assets/source plan | bundling commercial IWAD or forbidden branding |

## Approval requirements

Operator signoff and date, task ID, authorized person/tool, immutable source commit and permitted workspace; permissions, network access and file paths, data retention, stop conditions, exact rollback. Each record expires at operator-chosen condition. `null` or empty means NOT AUTHORIZED. Any agent must refuse task dispatch beyond authorized scope and return a proposed work order instead.

## Hard restrictions

No background work, local commands on user's PC, engine build, tests, source changes, device changes, GitHub commits or private-data exports are performed by this documentation. `AUTH-I` may only be granted in a **separate future explicitly authorized implementation task**; WO-F never grants it.
