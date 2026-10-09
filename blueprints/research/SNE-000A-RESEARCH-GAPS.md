# Remaining research gaps after first source inspection

**Priority P0**

- P0-01: Read entire game WAD binary metadata and resulting PK3 packing; current evidence is only scripts, filenames, comments and builder/validator source.
- P0-02: Inspect full gameplay class/call graph to ensure no load-bearing custom actor/weapon/HUD is absent from Tier-A matrix.
- P0-03: Verify actual GZDoom 4.14.2 baseline, then chosen candidate build, game parse and runtime on the operator's hardware; requires separate implementation/benchmark authorization.
- P0-04: Enumerate per-file, bundled library, asset and branding licenses, and code-import provenance before redistribution.
- P0-05: Define strict synthetic handoff input envelope; cap size, reject malformed payloads and avoid real ancestry in tests.

**Priority P1**

- P1-01: Map saved-state behavior across MAP01–03 and potential hub returns.
- P1-02: Compare fork update cadence and divergence using commit/CI history, not popularity.
- P1-03: Investigate BiasedDoom's glTF feature flag and CPU/GPU cost on Intel UHD 620.
- P1-04: Inspect ZDaemon compatibility separately from standard GZDoom workflows.
- P1-05: Verify the original Doom historical source-header licensing in the planned redistribution context.

Unresolved gaps remain open; all upstream selection scores must remain blank until review gates pass.
