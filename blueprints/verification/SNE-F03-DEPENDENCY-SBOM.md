# F-03 — Dependency and supply-chain readiness

## Separate dependency classes

1. **Host tools:** Visual Studio Build Tools/MSVC, Windows SDK, CMake, optional Ninja, Python for UZDoom build scripts; record file/product versions and approved rights.
2. **Source trees:** Git commit, nested submodules and any generated resource source; each immutable reference must be tied to candidate lane.
3. **CMake packages:** BZip2, VPX, OpenAL, ZMusic, cppdap, ABSEIL or other candidate-specific libraries as actually required by root and included CMake modules; don't invent a complete list from the root alone.
4. **vcpkg:** when a candidate has an actual pin/manifest, record registry baseline/port hashes, triplet, features, license; missing root `vcpkg.json` means inspect actual dependency mechanism rather than fabricate it.
5. **Runtime distribution:** EXE, DLL, engine PK3, fonts/shaders/translations, codec/graphics sidecars, resource rights and CRT linkage.
6. **External game assets:** original game PK3 and lawful commercial IWAD belong only to separately approved gameplay scope, not build ZIP or public artifact.

## Security conditions

- Network default DENY; no auto-fetch/first-use download unless new signed request lists exact source URI, checksum, expected size and legal terms.
- No `winget install`, bootstrap downloader, administrator elevation, executable fetched from unknown mirror, automatic license acceptance or system PATH changes.
- Record compiler and package diagnostics without full user home paths, secrets, serials or personally identifying data in public Git.
- A missing/ambiguous transitive license leaves `P00-G2: NOT CLEARED`, independent of a successful compilation.

## Output

One proposed row per dependency in `templates/SNE-F03-DEPENDENCY-ROW.json`, including original provenance, pinned revision, mode (vendored/system/vcpkg), arch, compiler ABI, NOTICE/license status and unknowns. No SBOM has been completed by this package.
