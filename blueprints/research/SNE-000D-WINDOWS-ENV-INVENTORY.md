# WO-000D — Windows 11 toolchain inventory checklist

**All actual versions: UNKNOWN UNTIL OPERATOR CAPTURE.** The reported Dell Latitude 5400 / Windows 11 / Intel UHD 620 profile is metadata, not an inspection of the current workstation.

## Inventory fields (read-only future preflight)

| Domain | Record exactly | Why it matters |
|---|---|---|
| Windows | edition, build, UBR, system architecture, update state | driver/SDK/toolchain parity |
| CPU | i5-8365U report, logical cores, sustained clocks, temperature | CPU-bound scene and compile time |
| GPU | PCI/device ID, UHD 620, driver provider/version/date, exposed GL/Vulkan APIs | choose available render backend, not assumed features |
| Memory | total, RAM channels if verified, free/commit, shared GPU utilization | iGPU memory bandwidth |
| Power | AC adapter, power plan/mode, battery percentage, thermal throttling | removes power-related skew |
| Firmware | BIOS revision, secure boot and related configuration (read only) | environmental provenance |
| Compiler | Visual Studio/Build Tools SKU, `cl.exe` path and MSVC version, target x64 toolset | C++17 / C++20 feasibility |
| SDK | Windows SDK exact installed versions, platform headers/libraries | linker and platform config |
| Build tools | CMake, Ninja, Git, Python path+version, PowerShell version | build generation and UZDoom scripts |
| vcpkg | cloned repo commit, baseline, triplet, manifest mode, cache location | pin transitive dependencies |
| External runtime | Visual C++ runtime state, graphics settings, defender exclusions (do not change) | failure triage |
| Engine resources | source SHA, submodule SHA, resource PK3 SHA, case-sensitive paths | eliminate hidden fallback |

## Collection methodology

The operator may, **after separate authorization**, use Windows GUI About/Display Adapter diagnostics, Visual Studio Installer details, CMake configure logs and signed binary properties. Uninstalled software should be recorded as `MISSING`; do not install or guess. If network downloads are required, approve host/domain/hash first. Log locations of compiler and executable privately, but replace personal home-folder path with `<USER_HOME>` in any public report.

## Snapshot schema

Fill `templates/SNE-000D-HARDWARE-RECORD.json`. Unknown numeric/version fields remain `null`, not a fake zero. Save full raw diagnostics outside the planning repo unless curated and redacted. Timestamp and audit who captured each fact.

## Do not do

No PowerShell settings reset, global `PATH` edits, package-manager installs, driver changes, `git reset`, engine checkout or benchmark until expressly approved. Windows native and WSL builds are different lanes: do not claim a WSL compile validates native Windows compatibility.
