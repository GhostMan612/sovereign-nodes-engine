# F-03 — Preventing silent dependency and configuration drift

A fixed engine Git SHA does **not** freeze third-party dependencies if CMake/vcpkg resolves a moving port, downloads a zip during configure or uses system libraries with changing versions. Future approved builds must pin the exact **resolved** dependency closure, checksums and version/ABI, not merely a package name.

Audit change in: Windows SDK, MSVC tools patch/build, Python interpreter path/version, vcpkg Git commit and baseline/features/triplet, CMake version, source submodules, generated resource tools, compile-time feature flags and environment variables. Record actual selected build targets and runtime sidecars.

When a package is missing, do not request default web fetch or `git submodule update --remote`: require a separate network/dependency approval and a source/rights re-evaluation. Do not silently turn optional Python/glTF/updater/nonfree assets ON/OFF to make compilation succeed; option revisions need an amended scope and an independent trial ID.

If two attempts disagree in inputs, compare as *different configurations*, not as evidence of a reproducibility failure under identical inputs.
