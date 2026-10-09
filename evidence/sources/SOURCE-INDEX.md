# Phase 00 source index — v0.6.0

Review states are source-specific and **not build/runtime results**. Earlier WO-A/B/C pin records stay historical, not overwritten by recent document status.

| Source ledger or record | Scope | Current classification |
|---|---|---|
| `SNE-REVISION-LEDGER.md`, `SNE-SRC-*-001.md` | initial game and engine reconnaissance | PINNED SELECTED SOURCE |
| `SNE-SOURCE-PINS-000B.md`, `SNE-SRC-*-002.md` | engine architecture, licenses, glTF/voxels | PINNED SELECTED SOURCE |
| `SNE-000C-PIN-LEDGER.md`, `SNE-SRC-*-003.md` | game compatibility, world and rendering hazards | PINNED SELECTED SOURCE |
| `SNE-000D-PIN-LEDGER.md` | native Windows root CMake/manifest/README source pins | PINNED SOURCE / READ-ONLY |
| `SNE-SRC-GZDOOM-004.md` | GZ C++17/vcpkg features and dependencies | SOURCE-OBSERVED |
| `SNE-SRC-UZDOOM-004.md` | UZ C++20, updater, LTO, build Python | SOURCE-OBSERVED |
| `SNE-SRC-BIASEDDOOM-004.md` | BD C++17, glTF/fastgltf, optional unsandboxed Python | SOURCE-OBSERVED |

## Missing evidence

Actual local Windows tool inventory; complete upstream dependency subtree and effective licenses; source binary and resource hashes; valid official IWAD test provenance; C-001…C-008 pass; Intel UHD 620 frame-time traces; independently approved distribution plan and ADR. **No engine candidate recommended as accepted foundation.**
