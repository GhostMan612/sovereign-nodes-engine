# WO-E — Candidate-specific architectural tradeoffs

## GZDoom

- Strong current-fit hypothesis: source game targets ZDoom/GZDoom 4.14 constructs; pinned source contains actor, voxel, light and hub code paths.
- Negative space: do not infer modern glTF or true world streaming from older model/hub structures.
- Main uncertainty: script and sprite fidelity on the actual source game, build dependencies, low-end GPU performance and sustainable fork changes.

## UZDoom

- Similar inherited game systems, distinct C++20 codebase and release-build LTO configuration; require independent configure/build and parity evidence.
- Upstream AI-assisted code/art contributions prohibited in its `CONTRIBUTING.md`. Policy may constrain upstream participation even when licensed downstream development is a distinct matter.
- Bundled code, updater/third-party dependencies and brand assets require complete rights analysis.

## BiasedDoom

- `fastgltf`-backed source and documentation for glTF/animation, rich graphics options, and optional embedded CPython. Do not infer `.glb` embedded image parity or advanced animation performance.
- Python mod execution is process-trusted and not sandboxed; isolate testing and keep disabled in baseline.
- Feature complexity and reported future ZScript direction can raise long-term script compatibility risks. Current source/docs still describe ZScript, so do not claim it has been removed.

## Architecture preference is not product choice

Use GZDoom for first **experimental control** if operator approves; keep UZDoom and BiasedDoom separate and equally accountable to core pass criteria. The choice of shipping product remains **HOLD**.
