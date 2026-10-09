# Reuse vs rewrite — reconnaissance decision hypotheses

**State:** ARCHITECTURAL HYPOTHESES, not approved implementation.

| Capability | First option | Why | Rewrite trigger |
|---|---|---|---|
| WAD/PK3 loading | Existing GZDoom-family VFS and map loaders | Existing content and gameplay depend on semantics | Unavoidable fatal incompatibility shown by repeatable test |
| ZScript/actors | Preserve existing VM and gameplay classes | High rewrite cost, core Tier-A contract | Agent demonstrates a concrete blocker and alternatives |
| GLDEFS/dynamic lights | Extend upstream render controls | Definitions already exist in game; GZDoom source has parser | Measured perf/correctness gap not solvable by settings |
| Voxel entities | Reuse `voxels.cpp` / `models_voxel.cpp` | Concrete source implementation | Required format, scale, collision or draw capability missing |
| glTF/animation | Isolated importer behind existing model API; study BiasedDoom | Conditional source implementation available | Proven upstream path impossible to adapt lawfully/maintainably |
| World continuity | Logical zone registry + standard transitions | Already MAP01–03; preserves level semantics | User explicitly prioritizes simultaneous visible zones over compatibility |
| Mantle bridge | Synthetic, read-only snapshot adapter | Decouples genealogy platform; preserves trust boundary | Never tie game directly to private mutable ledger |
| Physics/AI | Inherited engine behavior | Existing gameplay scripts require parity | Isolated subsystem demonstrates measurable need |

## Modularity

Start with logical interfaces and a small patch surface inside a retained upstream tree. Do not import one port's large C++ subtree blindly into another; compare ownership, licensing and build graph first. Prototype new terrain streaming separately rather than making it a hard dependency of a playable FPS.

## Hardware envelope

For Intel UHD 620: prioritize baseline profile, voxel *models*, limited dynamic lights and tested frame times before advanced shadows. No benchmark results exist; any FPS estimate would be speculative.
