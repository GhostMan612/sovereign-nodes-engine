# Tier-A and extended compatibility matrix

All execution results: **NOT RUN**. Do not mark PASS based on filenames or parser documentation.

| ID | Priority | Scenario | Evidence required |
|---|---|---|---|
| C-001 | Blocking | Engine boots custom PK3 rather than base IWAD map | known custom MAP01 marker + log/screenshots |
| C-002 | Blocking | `MAPINFO version "4.14"` and all three `addfragments` loads | no ZScript errors; custom actor behavior |
| C-003 | Blocking | MAP01 → MAP02 → MAP03 | transitions recorded; correct map identity |
| C-004 | Blocking | Custom Inventory/weapon/altar sprites | expected sprite frames and gameplay event |
| C-005 | Blocking | `GLDEFS` pointlights attached to actor sprite frames | visible/rendered lighting evidence and selected backend |
| C-006 | Blocking | Synthetic Godot→Doom handoff v1 received | producer/consumer run ID matches; invalid schema refused |
| C-007 | Blocking | HUD runtime reacts to player state | visual + behavior proof, no missing class |
| C-008 | Blocking | Existing generated WADs pass validator | source generator output + parser checks |
| C-009 | High | Save/load across map progression | deterministic mission + player state validated |
| C-010 | High | Renderer switching and fallback | startup/render proof OpenGL; Vulkan optional |
| C-011 | High | Voxels on enemies, pickups, weapon | actor behavior unchanged and model renders |
| C-012 | High | Dynamic light count stress | frame times, dropped frames, validation of bounds |
| C-013 | Medium | Third-party Doom/WAD compatibility | selected safe test cases; scope documented |
| C-014 | High | ZDaemon multiplayer compatibility | separate engine/target capability contract; never presume GZDoom parity |
| C-015 | High | Handoff tamper/corrupt input | rejects safely; no private data logs |

## How to test

Use actual same revision of Sovereign Nodes FPS packaged by its own verified build tooling, same IWAD rights, deterministic test route, same graphics resolution and repeatable capture method. Capture engine commit, game commit, OS/driver, complete command, render profile, test data hash, logs and result. No local tests were performed when authoring this overlay.
