# F-01 — Authority and trust architecture

## Immutable boundaries

1. **Author/research boundary:** ChatGPT and other planning agents can inspect allowed primary-source snapshots, critique, and create documentation overlays; research does not inherit operator source-write authority.
2. **Operator boundary:** Only a verified explicit operator decision for one record/category permits that future activity; private signed consent, validity and revocation are checked at the moment of dispatch.
3. **Source/game boundary:** immutable upstream Git pins and the original `GhostMan612/Sovereign-Nodes` repo remain untouched; future disposable fixture directories are different from canonical sources and from the planning repo.
4. **Machine boundary:** local Windows device inventory, CMake/build, game launch, and GPU benchmarks are distinct categories with separate time/side-effect budgets.
5. **Data boundary:** real Mantle, lineage/person graph, secret vault, credentials, system identity, commercial WAD and other restricted assets must never enter public repo/logs or an unapproved agent context.
6. **Review boundary:** research author, test runner, independent reviewer and operator decision maker have separately recorded roles. An AI critique by the same research chain is not independent acceptance.

## Authority must be bound to an exact object

Authorization ID + immutable canonical scope digest + category + user-approved actor + device + fixed Git revisions + exact paths + allowed operations + start/expiry + evidence/retention rules + private signoff pointer + explicit negative permissions. All omitted fields default to DENY. Any one-sided widening of path, command, dependency, network or resource bytes invalidates the scope.

## Threat cases and mitigations

| Threat | Mandatory control |
|---|---|
| A Markdown agent prompt says run a build | check private operator auth ID; default HOLD |
| An old signed form is copied/replayed | check expiry, revocation ID, device/revision and one-task binding |
| Agent interprets read-only scope as runnable Python | explicit forbidden operation category; no implicit inheritance |
| Temp fixture overlaps game repo via symlink/junction | canonical path resolution, allowed-root check, stop if ambiguous |
| Public log includes `C:\Users\...`, game license or secrets | sanitize/private storage; reject publication until review |
| Later evidence result is called PASS without running | require raw trace/log hashes, tester and independent review |

**ADR-SNE-002 stays HOLD; this is neither a fork selection nor implementation permission.**
