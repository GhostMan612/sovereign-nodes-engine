# F-01 — Proposed `AUTH-H` non-invasive Windows inventory

**State: FUTURE CONDITIONAL / NOT AUTHORIZED OR RUN.** Even a user's named laptop in a plan is not proof of current OS, driver, SDK or installed compiler.

## Inputs required before request

- Device selected by operator (reported Dell Latitude 5400, i5-8365U, 16 GiB, UHD 620 only as a *reported reference*).
- Explicit allowlist of read-only metadata categories: Windows build, CPU/GPU/driver, RAM, VC++ compiler/Visual Studio, CMake, Ninja, Git, Python, Windows SDK, OpenGL/Vulkan backend *only if readable without launching an engine*.
- Private results root, permitted commands or GUI inspection steps, start/end, redacted summary fields and separate review role.

## Exclusions

No driver install/update, global PATH/config edit, Visual Studio install, vcpkg bootstrap, package download, source clone, engine/game launch, registry mutation, MSVC build, firewall/Defender change, optional telemetry or native GPU stress. If a check is not already available, record `TOOL_NOT_INSTALLED` rather than installing it.

## Evidence output

At least one sealed inventory record using the WO-D `SNE-000D-HARDWARE-RECORD.json` template adapted for operator-selected non-sensitive fields; list exact command (after authorization), exit status, redacted result, collection timestamp, machine profile ID and screenshot/log private SHA-256. No hostnames, local user paths, key material, serials or full device IDs in public Git. Leave unknown values null.

## Admission to F-03

The inventory is necessary but insufficient for a future build. F-03 requires a separate `AUTH-B`, resolved versions, pinned transitive dependencies and no inherited permissions.
