# WO-F — Noninvasive hardware/environment inventory specification

**State: NOT CAPTURED.** The user reports a Dell Latitude 5400, i5-8365U, 16 GB RAM, Intel UHD 620, Windows 11 Pro. These reported details are not a fresh host capture or a measured rendering capability. The exact versions remain unknown to this package.

## Field inventory for a future separately authorized read-only capture

| Area | Required fields | Pitfall |
|---|---|---|
| OS and build | Windows edition, full build, x64 arch | avoid stale screenshots or partial version |
| CPU | CPU model, logical cores, sustained clock/throttle info | nominal turbo != sustained |
| RAM | installed GB, channel layout if accessible, memory pressure | UHD 620 uses shared memory |
| GPU | PCI hardware ID optional/redacted, Intel driver version/date | OpenGL/Vulkan availability is not assumed |
| BIOS/firmware | version and date | no automatic BIOS updates |
| Toolchain | MSVC toolset, SDK, CMake, Ninja, Git, Python build interpreter | WSL toolchain != native MSVC |
| Power | AC vs battery, Windows power mode, thermal/cooling state | variance can reverse benchmark ranking |
| Renderer | actual engine-selected graphics API and options | UI setting alone is not proof |
| Capture program | method/version, frame timestamp resolution, sample count | FPS overlay alone insufficient |
| Executables | engine binary SHA-256, PK3 SHA-256, approved IWAD provenance | do not publish licensed assets |

## Future record security

Only sanitized machine-level metadata without username, serial number, device address, Windows product key, user directory path, secrets, or genealogy may be committed. Raw logs stay local under a separately approved location and retention plan. No hardware probing/setting changes are authorized by this document.

Use historical blank `templates/SNE-000D-HARDWARE-RECORD.json` during a future authorized capture. Do not fill fields from memory as if measured today.
