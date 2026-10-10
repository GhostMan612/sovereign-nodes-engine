# WO-F — Dependency, rights, upstream policy and maintenance closure

**Status: PARTIAL RESEARCH / NO DISTRIBUTION CLEARANCE.** Not legal advice. No engine/source release or proprietary game data is part of WO-F.

## Candidate-specific obligations

- GZDoom: root GPL and file-specific historical BSD/LGPL notices; enumerate built-in libraries, resource PK3s, textures/shaders/audio/fonts, dependency origins and notices, and modifications before any distribution.
- UZDoom: GPL and per-file notices, independent asset/branding rights, C++20/Abseil and optional updater dependencies; inspected upstream contribution guidance rejects AI-assisted upstream PRs. A downstream license-compliant fork and its maintenance cost must be evaluated separately.
- BiasedDoom: fastgltf/CPython and optional audio packages; source and binary feature manifests; embedded Python can access native-equivalent host powers and is not a sandbox. Baseline should request Python OFF, verify actual compiled/runtime behavior, and avoid loading unknown mods.
- ZDaemon: separate native compatibility and licensing lane; don't infer ZScript, voxel, hub or graphic parity from GZDoom.

## Independent rights checklist

1. Enumerate each included executable, DLL/static library, resource archive, shader, font, model, logo, launcher and updater by SHA and rights owner.
2. Record immutable source commit, fetched package version, license identifier/full notice source and redistribution duties; unknown or conflicting licenses block release.
3. Keep commercial IWAD bytes outside Git/ZIP and only reference lawful local copies for tests.
4. Identify GPL source availability, attribution, changes and source offer duties for the contemplated delivery model; account for per-file notice exceptions.
5. Require separate branding/trademark clearance and independent review of code versus documentation/image licensing.
6. Define patch/update burden: CI, merge conflicts, security update tracking, downstream maintenance capacity and rollback to a known compatible binary.

## State semantics

`SBOM WRITTEN` is not `LICENSE APPROVED`. A test-only local experiment does not automatically authorize distribution or upstream contribution. Gate G2 remains OPEN until the independently reviewed full dependency and asset inventory is accepted by operator.
