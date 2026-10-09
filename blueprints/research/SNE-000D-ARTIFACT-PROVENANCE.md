# WO-000D — Provenance chain for binary and game evidence

An auditable gameplay benchmark requires **five separate identities**:

1. Engine source `git rev-parse HEAD` (40 hex), clean/dirty state and patches.
2. Toolchain manifest snapshot (MSVC, CMake, SDK, vcpkg, flags, generator, compiled feature toggles).
3. Engine binary SHA-256 **plus** required resource PK3/DLL hashes, not just executable filename.
4. Game content hash: Sovereign Nodes FPS source pin, packager tool hashes, PK3 SHA-256, included WAD hashes and a legally acquired IWAD's hash/provenance (never copy the IWAD into SNE Git).
5. Test environment and trace identity: OS/GPU driver/AC state/backend, scene/route/seed, raw trace checksum, metrics algorithm, tester and time.

## Acceptable evidence dispositions

| Status | Meaning |
|---|---|
| `SOURCE_OBSERVED` | code/doc file at pin inspected; behavior not executed |
| `BLUEPRINT_VALIDATED` | overlay integrity, docs and templates checked; no runtime claim |
| `ENV_CAPTURED` | target-machine metadata independently recorded |
| `CONFIGURED` | actual CMake configure command and exit-code/log captured |
| `BUILT` | binary/resources produced with identities and completed build logs |
| `GAME_PARITY_PASS` | C-001…C-008 evidence independently accepted |
| `BENCHMARK_CAPTURED` | valid frame-time traces, replicates and stable environment |
| `LICENSE_REVIEWED` | external license/asset reviewer accepted distribution terms |
| `OPERATOR_ACCEPTED` | explicit owner decision with date and scope |

These statuses are **not interchangeable** and may not be automatically promoted by documentation, commits or model-generated interpretations. Preserve unredacted machine-local trace outside a public repo; curate only non-sensitive hashes and metrics.
