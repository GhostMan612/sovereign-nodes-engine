# SNE-WO-000D — Hardware and Windows build reproducibility blueprint

- Phase: SNE-P00; release: v0.6.0; package: SNE-WO-000D-RESEARCH-0006
- Baseline SNE repo: `706db57a4fbabd701244dd9e4674a59f7ab044f3` (`main`)
- Status: RESEARCH BLUEPRINT AUTHORED / OPERATOR TESTS NOT RUN / FORMAL ACCEPTANCE PENDING
- Authority: operator controls Windows installs, engine compilation, runtime testing, approval and manual Git push
- Scope: source-backed build configuration analysis, dependency closure plans, UHD 620 benchmark method and evidence templates

## Objective

Make GZDoom, UZDoom and BiasedDoom reproducible test candidates **without** claiming that they have built or run on the operator's Windows 11 laptop. The package records pinned source revisions and exact preflight questions, build-lane differences, command *templates* subject to separate operator approval, run-log schemas, operational guardrails, test-scene normalization, and the Phase 00 G4/G5 evidence gate.

## Explicit non-goals

No engine repo fork, checkout, dependency installation, compiler invocation, graphics driver change, executable or WAD generation, benchmark execution, GPU score invention, ZDaemon parity promise, real Mantle data, or proprietary IWAD in version control. Nothing here authorizes the operator's shell or coding agents to run an engine build.

## Primary deliverables

1. `SNE-000D-WINDOWS-ENV-INVENTORY.md`, `SNE-000D-BUILD-LANE-MATRIX.md`, `SNE-000D-CMAKE-OPTIONS.md` and `SNE-000D-REPRO-BUILD-COMMANDS.md`: auditable toolchain lanes with unverified configuration steps clearly labeled.
2. `SNE-000D-DEPENDENCY-LOCK-PROTOCOL.md` plus `SNE-000D-THREAT-LICENSE-CHECKLIST.md`: track source, submodule, vcpkg, transitive dependencies, licenses and asset provenance.
3. `HARDWARE-BENCHMARK-PLAN.md`, `SNE-000D-MEASUREMENT-SOP.md`, `SNE-000D-TEST-SCENES.md`, `SNE-000D-PERFORMANCE-DECISION-GATES.md`: operator-controlled, frame-time-based measurement design.
4. `templates/SNE-000D-*.json`: blank, machine-readable records using `null` for unknown quantities; never mock measurement success.
5. Source pins, verification/acceptance checklists and clear escalation to WO-000E foundation ADR.

## Ordered review and future execution gates

- **D0 Research envelope:** validate source links, files and documentation ZIP; no runtime proof.
- **D1 Owner preflight authorization (future):** choose one candidate and approve toolchain inventory scope. Record exact approved locations and commands.
- **D2 Windows toolchain inventory (future):** actual OS build, MSVC/toolset, CMake, Ninja, SDK, CPU/GPU/driver, library and memory details; mark unavailable tools as MISSING, not installed.
- **D3 Dependency/SBOM closure (future):** confirm all hashes, transitive dependencies, static/runtime linkage and redistribution notices.
- **D4 Source build (future separate authorization):** isolated working clone, pinned sources, explicit configure/build, capture stdout/stderr, exit codes and artifacts; no agent-produced build under SNE Phase 00.
- **D5 Tier-A game correctness (future):** C-001…C-008 must be demonstrated first, including custom-map anti-fallback control and synthetic handoff.
- **D6 UHD 620 comparison (future):** controlled P0/P1/P2/P3 and L0/L1/L2/L3 captures with matched content, scene, power and driver.
- **D7 Independent review:** independent verifier checks reproducibility and data quality; operator signs any accepted result.

Do not skip D5 merely because a candidate boots stock Doom. No benchmark qualifies as a foundation decision if C-001…C-008 fail.

## Exit criteria for this documentation-only work order

Every approved future command lane has prerequisite and stop conditions; each metric has a measurement definition and schema; source claims have commit/file pins; logging/asset security boundaries are explicit; work order's runtime status remains NOT RUN. This is **blueprint completeness**, not D4/D6 PASS.

## Handoff

Independent research review and owner gate: `artifact-chain/acceptance/SNE-ACC-000D.md`, `governance/WO-000D-REVIEW-FINDINGS.md`. Proposed WO-000E (foundation ADR) must explicitly record missing runtime evidence or be blocked. Neither source-only audit nor packaging can adopt ADR-SNE-002.
