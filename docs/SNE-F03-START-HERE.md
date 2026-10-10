# F-03 / v1.2.0 — Start here

The SNE-F03 ZIP is a **build-readiness blueprint**, not a compiled engine, run report, test permission, or ADR choice. Previous operator-pushed SNE HEAD: `f2f2cfec676b9a5254fa2a5a7e6f08198581fa09`.

Read in order: `artifact-chain/work-orders/SNE-WO-F03.md` → `blueprints/verification/SNE-F03-ADMISSION.md` → `SNE-F03-WINDOWS-TOOLCHAIN.md` → three engine lane documents → `SNE-F03-REPRODUCIBILITY-TRIALS.md` → `SNE-F03-F04-ENTRY.md` → `governance/SNE-F03-AUTHORIZATION-REQUEST.md`.

**Prioritize evidence over another installation:** after publishing this blueprint, the first *real* activity should be operator-approved `AUTH-H` read-only inventory (or independent `AUTH-R` reviewer), not an engine build. The provided host/template fields are blank and no one has verified Visual Studio, CMake, GPU, Windows SDK or dependencies on the actual laptop.

Never put proprietary IWAD bytes, private resource paths, output binaries, raw build logs or signed private records in this planning repo. `SNE-F03-INSTALL.md` provides exact extraction/staging instructions. Confirm package preimages before overlay extraction.
