# SNE-SRC-GZDOOM-004 — GZDoom Windows compilation probe

**Repo:** `ZDoom/gzdoom` at `c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7`; **status:** SOURCE-OBSERVED / NEVER BUILT.

- [Root CMake](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/CMakeLists.txt) lines 1, 27–50: minimum CMake 3.16, C++17, Windows-targeted `x64-windows-static` default when no triplet; MSVC CRT mode when supported.
- Same CMake lines 217–223: BZip2, VPX, cppdap, ZMusic lookup paths; bundled/source fallbacks below root require independent review.
- [vcpkg manifest](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/vcpkg.json) contains optional libvpx and OpenAL Soft dependency features; do not assume those are enabled unless flags recorded.

**Hypothesis:** Windows-native MSVC x64 source build can form an apples-to-apples C++17 baseline. Unknown: available VS/Windows SDK, packaged PK3 resources, toolchain version, current GPU backend, exact dependency graph, build success, custom-game parity. No score assigned.

**Future gate:** record locked source/deps/flags, actual configure/build output, binary+resource hashes, then C-001…C-008. No benchmark just on a successful vanilla IWAD launch.
