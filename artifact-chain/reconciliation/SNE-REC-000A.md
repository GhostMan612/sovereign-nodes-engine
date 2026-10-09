# SNE-REC-000A — Research reconciliation

| Topic | Prior assumption | New source evidence | Disposition |
|---|---|---|---|
| Game SHA | Not pinned in v0.2 inventory | Game `44034e97...` pinned | UPDATE SOURCE INVENTORY |
| GZDoom voxels | General public feature | `src/common/models/voxels.cpp`, `models_voxel.cpp`, `src/r_data/voxeldef.cpp` | REUSE STUDY |
| BiasedDoom glTF | README claim only | Conditional `model_gltf.cpp/.h`, fastgltf include | SOURCE FOUND; RUNTIME PENDING |
| UZDoom AI policy | Unverified risk | `CONTRIBUTING.md` prohibits AI-assisted upstream PRs | UPSTREAM SUBMISSION RESTRICTED; PRIVATE FORK QUESTION SEPARATE |
| Godot→Doom handoff | Reader claimed present | Both writer and reader inspected; same schema 1 and temp path visible | SOURCE LINK PROVEN; E2E PENDING |
| WAD `dirofs=12` | Sometimes described as Doom universal law | Source validator requires it for its generator | CLASSIFY AS PROJECT CONSTRAINT |
| Work order nomenclature | 000A called engine research informally | 000A is **game inventory**, 000B is **upstream engine audit** | 000B RESEARCH ONLY SEEDED |

No game fixes or code patches have been made. This record prevents speculative research from being promoted to a verified implementation claim.
