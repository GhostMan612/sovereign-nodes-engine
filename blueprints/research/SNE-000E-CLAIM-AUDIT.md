# WO-E — Adversarial claim audit A–D

| Claim ID | Earlier tempting inference | Source-grounded status | Correct disposition / falsifying evidence |
|---|---|---|---|
| CL-01 | Git commit means work order fully accepted | FALSE EQUIVALENCE: A–D acceptance records remain open | publication is not reviewer/operator signoff |
| CL-02 | Engine boots, so the game's PK3 loaded | UNSUPPORTED | C-001 custom GapNode marker vs stock IWAD Entryway |
| CL-03 | Files named `ORESHAA0`, `TOOLAA0` render intended actors | HIGH-RISK HYPOTHESIS | inspect 4-letter sprite prefix parser and packed sprite names; C-004 |
| CL-04 | GLDEFS pointlight declaration guarantees emitted light | UNSUPPORTED | distinguish light declaration, frame binding and actor in view; C-005 |
| CL-05 | Integer scanner correctly parses JSON `true`/`false` | HIGH-RISK HYPOTHESIS | synthetic true/false plus missing/stale versions; C-006/C-015 |
| CL-06 | MAPINFO maps 01–03 imply true seamless world | INCORRECT | logical transitions and hub persistence are not simultaneous physical streaming; C-003/C-009 |
| CL-07 | Engine source supports voxels, so dynamic actor model swap always works | INFERRED | VOXELDEF scene, player weapon, collision and save tests; C-011 |
| CL-08 | BiasedDoom README glTF means all 2.0 assets render | DOC-CLAIM + CONDITIONAL SOURCE | compile flags, model registration, external and embedded texture tests |
| CL-09 | BiasedDoom's embedded Python is sandboxed | FALSE per author documentation | opt-in Python is equivalent to trusted executable, not untrusted mod mechanism |
| CL-10 | UZDoom Python CMake requirement provides gameplay Python | UNSUPPORTED | Python build script dependency distinct from game runtime |
| CL-11 | UZDoom no-AI upstream PR policy prohibits a GPL-licensed independent fork | FALSE CONFLATION | separate contribution guidelines from downstream license obligations |
| CL-12 | `dirofs == 12` is a Doom/WAD format universal | PREVIOUSLY CORRECTED | only generator-specific writer invariant, not all WADs |
| CL-13 | 30/60 FPS target is observed UHD 620 performance | FALSE | provisional thresholds, no on-device traces |
| CL-14 | Low average FPS means candidate always inferior | UNSUPPORTED | frame-time percentiles, output equivalence, thermal and driver controls |
| CL-15 | Renderer/camera upgrades can preserve savegame/demo/network compatibility automatically | UNSUPPORTED | separate save/load, replay, ZDaemon and interaction tests |
| CL-16 | Main project GPL LICENSE covers all included brand art/mod assets | UNSUPPORTED | full asset provenance and third-party/transitive SBOM required |
| CL-17 | Research author self-review fulfills independent gate | FALSE | distinct reviewer, signed objections, operator disposition |
| CL-18 | All A–D code paths were exhaustively inspected | OVERCLAIM | selected pinned files only; further source and device work |
| CL-19 | CMake configure/build commands are already proven | FALSE | WO-D commands are future gated templates, not run |
| CL-20 | Updated developer tools automatically make engine runnable on laptop | UNSUPPORTED | exact installed SDK/driver/compiler inventory required |

**Audit class:** AUTHOR RED-TEAM; not a second independent reviewer. Full independent recheck procedure in `governance/WO-000E-INDEPENDENT-REVIEW-PROTOCOL.md`.
