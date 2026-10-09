# SRC-CLASSIC-001 — Original Doom and Chocolate Doom

**Chocolate Doom:** `895f581c5d91497bdda0516612da803fe5843e28`
**Original Doom:** `a77dfb96cb91780ca334d0d4cfd86957558007e0`
**Status:** SOURCE READ / IMPLEMENTATION NOT EXECUTED.

## Chocolate Doom

- [`src/doom/p_setup.c`](https://github.com/chocolate-doom/chocolate-doom/blob/895f581c5d91497bdda0516612da803fe5843e28/src/doom/p_setup.c) — Loads WAD geometry and BSP-related arrays, blockmap and reject visibility data.
- [`src/doom/p_maputl.c`](https://github.com/chocolate-doom/chocolate-doom/blob/895f581c5d91497bdda0516612da803fe5843e28/src/doom/p_maputl.c) — Movement and collision utility implementation.
- [`src/doom/r_data.c`](https://github.com/chocolate-doom/chocolate-doom/blob/895f581c5d91497bdda0516612da803fe5843e28/src/doom/r_data.c) — Sprite/wall rendering data preparation.
- [`CMakeLists.txt`](https://github.com/chocolate-doom/chocolate-doom/blob/895f581c5d91497bdda0516612da803fe5843e28/CMakeLists.txt) — C99; CMake 3.7.2; SDL2, SDL2_mixer and SDL2_net configurations.

## Original Doom

- [`linuxdoom-1.10/p_setup.c`](https://github.com/id-Software/DOOM/blob/a77dfb96cb91780ca334d0d4cfd86957558007e0/linuxdoom-1.10/p_setup.c) — Original WAD geometry, BLOCKMAP and REJECT loading reference.
- [`linuxdoom-1.10/README.b`](https://github.com/id-Software/DOOM/blob/a77dfb96cb91780ca334d0d4cfd86957558007e0/linuxdoom-1.10/README.b) — Historical source-distribution context warns the Linux snapshot differs from the final DOS game.
- [`README.TXT`](https://github.com/id-Software/DOOM/blob/a77dfb96cb91780ca334d0d4cfd86957558007e0/README.TXT) — Historical release narrative plus later GPL notice at bottom.
- [`LICENSE.TXT`](https://github.com/id-Software/DOOM/blob/a77dfb96cb91780ca334d0d4cfd86957558007e0/LICENSE.TXT) — GPL version 2 included in repository; older individual source headers retain historical wording.

## Recommendation

Use this lane for learning fixed-timestep simulation, BSP, blockmap, collision, serialization assumptions, and to challenge renderer/world-design proposals. Neither offers ZScript parity or modern glTF/lighting without a major reimplementation.

**Rights warning:** Historical individual files in original Doom still contain old restrictive license-header text even though the repository now carries GPL-2 licensing. Legal provenance, file-header interpretation and commercial game data licensing must be reviewed before copying code into a distributable engine.
