# F-03 — Architecture boundaries of native Windows build work

## Source → output graph

- Frozen candidate Git source at named SHA **read-only**, plus exact submodule/dependency revisions and complete input file inventory.
- Operator-owned, separately approved Windows MSVC/Windows SDK toolchain and CMake generator.
- Per-candidate isolated build/cache tree (GZ-Release, UZ-Release, BD-base and optional BD-glTF **never share CMakeCache**).
- Generated runtime binary, DLLs, graphics/audio libraries and engine resource PK3 identities stored in private evidence.
- F-04 game launch requires a different approval and the original unmodified B0 PK3 plus legitimate external IWAD. F-03 success never supplies that automatically.

## Untouchable roots

`C:\sovereign-nodes-engine` is documentation-only; existing `GhostMan612/Sovereign-Nodes` checkout is immutable; third-party upstream source trees must be pinned and not mutated by proposed build commands. A future operator chooses actual absolute source/build/cache/evidence paths *outside* these areas. Relative paths, broad drive-root writes, symlink/reparse traversal or arbitrary install directories are forbidden.

## Invariants

1. A source pin is not a built executable identity; every produced artifact needs a byte SHA-256 and accurate provenance.
2. `CONFIGURE PASS` ≠ `BUILD PASS` ≠ `RESOURCE PASS` ≠ `C-001 PASS` ≠ `FPS PASS`.
3. Transitive package rights, CRT/static linkage and runtime sidecars must be understood before redistribution.
4. BiasedDoom native embedded Python is not a sandbox. Keep it OFF in baseline; glTF needs independent fastgltf inspection.
5. Source game/engine modifications are outside this blueprint and require `AUTH-I` or distinct approved repair order.
