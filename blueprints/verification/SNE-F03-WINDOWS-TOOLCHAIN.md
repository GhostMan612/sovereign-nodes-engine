# F-03 — Read-only native Windows toolchain inventory oracle

**Proposed future `AUTH-H` only; none queried or measured.** Reference host was reported as Dell Latitude 5400, i5-8365U, 16 GiB, UHD 620, Windows 11 Pro. Treat every actual software/driver value as unknown until captured.

| Identity | Capture only under approved `AUTH-H` | False inference to avoid |
|---|---|---|
| OS/architecture | Windows build, x64 capability, native vs WSL process | Windows 11 automatically implies functioning SDK |
| VS/MSVC | Installed VS instance, workloads, MSVC compiler target version, linker | `cl` absent on ordinary PATH proves no VS install |
| Windows SDK | SDK versions and approved target version | SDK installed means candidate compiles |
| CMake | binary version/path, generator list, cache provenance | CMake min 3.16 is validated compatibility for any newer CMake |
| Ninja | existing command and version if selected | Ninja generator can use uninitialized MSVC tools |
| Python | native executable/arch/version >=3.6 if UZ future build | WSL Python fulfills native Windows build automatically |
| vcpkg | actual commit, triplet, manifest feature resolution when relevant | every candidate has identical manifest and ports |
| GPU | UHD 620 driver/API information if cheaply available | actual Vulkan/OpenGL or FPS is proven |
| Power/disk/RAM | disk budget, thermal/power mode and memory | machine capacity sufficient for a build without measurement |

Future operator could approve *specific* read-only methods (e.g., VS locator, `cmake --version`, `Get-CimInstance`, `Get-Command`) via `SNE-F02-HOST-INVENTORY.md`. No commands are executed from this package. Never install missing tools to satisfy inventory; use `NOT DETECTED BY METHOD` and preserve non-sensitive error/exit evidence privately.
