# Upstream code reconnaissance — research map

## Observation status

The candidate repositories' public descriptions and top-level layout were reviewed on 2026-10-09. **No pinned checkout, full file-by-file code audit, dependency build, or execution occurred**. Treat paths below as starting hypotheses unless source directly documents them.

### GZDoom — https://github.com/ZDoom/gzdoom

- Published primary system: ZDoom-derived modding engine with OpenGL/Vulkan renderer and ZScript ecosystem.
- Public tree uses CMake (`CMakeLists.txt`), license records and source modules (`src/`).
- Search target in checkout: `src/` renderers, `src/common/models`, ZScript VM, archive/resource loading, ACS, map parser, GLDEFS light binding, save-game serialization.
- Exact location/signatures of extension seams: **UNVERIFIED**, must be pinned to commit and inspected.

### UZDoom — https://github.com/UZDoom/UZDoom

- Published architecture: GZDoom descendant with OpenGL/Vulkan, dynamic lighting, 3D floors, modding support.
- Published license: GPLv3-or-later; see actual `LICENSE` and third-party notices before redistribution.
- Follow the project's current wiki for Windows/VS/CMake/dependencies; **do not hardcode stale versions**.
- Policy question: determine contribution eligibility for AI-assisted changes separately from license eligibility for a private/local derivative.

### BiasedDoom — https://github.com/EricsonWillians/BiasedDoom

- Published implementation path for glTF loader: `src/common/models/model_gltf.*`, using `fastgltf` (README statement; verify actual symbols on pinned revision).
- Published features: `.gltf/.glb`, skeletal animation/GPU skinning paths, post-processing, procedural missions, opt-in CPython, ZScript/ACS currently supported.
- Published roadmap: author intends to deprecate ZScript; **not proof deprecation occurred**.
- Security question: confirm Python code permissions, filesystem/network access and app distribution consequences on a pinned build.
- Probe: compare changes against GZDoom ancestor before porting parts; licensing and dependency compatibility must be reviewed.

### Chocolate Doom — https://github.com/chocolate-doom/chocolate-doom

- Published philosophy: reproduce vanilla DOS behavior including bugs, saves and demo compatibility.
- Build system can use Autotools; Windows wiki describes MSYS2 and SDL dependencies, but documentation may be historical.
- Good architecture-reading source, **not** a candidate for a low-effort ZScript-preserving fork.

### Original Doom — https://github.com/id-Software/DOOM

- Reference for fixed-timestep simulation, WAD, BSP, sectors, visibility and collision concepts.
- Do not use original rendering code as evidence of modern model/shader support.

## Mandatory source-inspection worksheet

For EACH shortlisted engine capture: exact repo URL; commit SHA; license and packaged dependency licenses; compiler/CMake versions; renderer selection logic; model import classes; voxel loader; ZScript API/runtime; GLDEFS/map parsing; world changes; save serialization; procedural generation; test frameworks; third-party tooling; effort estimate; commit/path/symbol evidence.

Store reviewed findings in `evidence/sources/` and promote only confirmed statements into ADR-SNE-002.
