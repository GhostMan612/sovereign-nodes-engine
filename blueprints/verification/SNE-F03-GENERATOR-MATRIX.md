# F-03 — Generator, architecture, CRT and cache separation

| Dimension | VS 2022 generator proposal | Ninja proposal |
|---|---|---|
| Tool | `Visual Studio 17 2022` (`-A x64`) | `Ninja` with explicitly activated MSVC x64 environment |
| Config selection | multi-config `--config Release` | single-config `-DCMAKE_BUILD_TYPE=Release` at configure |
| Compiler identity | installed MSVC/Windows SDK and generator toolset | same toolchain *only if environment actually valid* |
| Output roots | dedicated GZ/UZ/BD each | different fresh GZ/UZ/BD trees again |
| CMakeCache | collect checksum/approved options | likewise, never reuse VS-generated cache |
| Runtime library | inspect actual `CMAKE_MSVC_RUNTIME_LIBRARY` and DLL/static packaging | verify same assumption in candidate CMake and binary imports |

Never pass VS-specific `-A x64` to Ninja. Never treat a Visual Studio generator name as installed without inventory. `CMAKE_BUILD_TYPE` does not select a Visual Studio multi-config release. Record compiler ABI, MSVC tools version, C++ standard, flags, link flags, static runtime and vcpkg target triplet per candidate.

For reproducibility, only compare two attempts as identical inputs when both toolchain, flags, environment, dependency versions, resource-generation settings and source revisions genuinely match. A different PDB path or timestamp can change hashes without changing functionality; investigate rather than masking differences.
