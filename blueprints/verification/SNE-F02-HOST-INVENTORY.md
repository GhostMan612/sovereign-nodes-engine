# F-02A — Proposed non-invasive Windows inventory (`AUTH-H` only)

**TEST-SPECIFIED / NOT AUTHORIZED / NOT RUN.** These command examples are for a *future exact allowlist* signed by the operator. Copying this document or its shell commands does not confer permission.

| Category | Potential read-only query (future) | Capture or limitation |
|---|---|---|
| OS | `Get-CimInstance Win32_OperatingSystem` | Caption, BuildNumber, OSArchitecture; redact local identifiers |
| CPU | `Get-CimInstance Win32_Processor` | Name, NumberOfCores, NumberOfLogicalProcessors only |
| GPU | `Get-CimInstance Win32_VideoController` | Name, DriverVersion, DriverDate, AdapterRAM **driver reports may be misleading on UMA** |
| Memory | `Get-CimInstance Win32_ComputerSystem` | TotalPhysicalMemory only; no hostname or user |
| CMake | `Get-Command cmake -ErrorAction SilentlyContinue` and `cmake --version` if found | binary version and location redacted |
| Ninja | `Get-Command ninja -ErrorAction SilentlyContinue`, `ninja --version` if found | missing is an observed absence, not FAIL |
| Git | `git --version` if allowed | no repository state modification |
| Python | `python --version` if found | distinguish Windows native vs WSL Python |
| MSVC/SDK | operator-reviewed VS/MSVC/Windows SDK inventory method, if installed | absence of `cl` on PATH alone does **not** prove absence of MSVC |
| Renderer | static driver capability info when accessible without game/benchmark | does **not** prove actual OpenGL/Vulkan backend runs |

No `winget`, installer, driver update, vcpkg bootstrap, environment mutation, system settings, registry write, engine launch, WSL distro install, network scan or GPU load. If any tool is absent, use `NOT INSTALLED / NOT DETECTED BY METHOD` with method; don't guess.

Preflight and private capture: approval record ID+digest, source host alias, timestamp UTC, stdout redaction, commands/exit status, sha256 of private raw capture, independent reviewer and file-retention policy. Use `templates/SNE-F02-HOST-INVENTORY.json`. A reported Latitude 5400/UHD 620 is a *reference profile*, not a measured scan.
