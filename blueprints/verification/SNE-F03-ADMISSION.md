# F-03 — Preflight admission checklist (ALL UNCHECKED)

**NOT AUTHORIZED; NOT RUN.** An installed text plan is not operator approval.

- [ ] Operator has assigned and verified an authentic, unrevoked, unexpired **`AUTH-H`** exact-scope approval; host metadata was collected under that scope.
- [ ] Host inventory records actual OS build/architecture, CPU, Intel GPU driver, RAM, Visual Studio + MSVC toolset, Windows SDK, CMake, chosen generator, Python interpreter for UZDoom and any vcpkg checkout.
- [ ] Qualified F-00 reviewer has signed source-critical findings or unresolved issues are explicitly held. Current evidence does not demonstrate this.
- [ ] Candidate source checkout SHA and all submodules locked; working tree clean and scope permits exact read/outputs.
- [ ] Build dependency provenance, SHA/versions, license notices, network/download policy and resource-package conditions reviewed; no unknown dependency auto-download.
- [ ] One **separate signed `AUTH-B`** identifies one candidate commit, exact immutable scope, actor, machine, toolchain, generator, flags, allowed commands, absolute input/output paths, time/size budgets, retention, rollback and stop conditions.
- [ ] Baseline compile options, CRT, architecture, generator and optional embedded runtimes explicitly recorded and *approved*; no arbitrary flag changes during trial.
- [ ] No unauthorized software installer, driver/SDK update, original game edit, real IWAD copy to repo or untrusted code execution.

**If any checkbox is unresolved, classify `BLOCKED` for actual builds.** Do not label an absent compiler a broken engine. The F-03 ZIP itself can be staged/committed without any of these test items becoming complete.
