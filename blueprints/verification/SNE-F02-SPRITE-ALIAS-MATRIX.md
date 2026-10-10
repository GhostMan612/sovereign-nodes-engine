# F-02B — B1 one-variable sprite identity and actor invariants

**Source hypothesis:** `core.zs` declares `ORE_FRAME = "ORESHAA0"` and `LOCATOR_FRAME = "TOOLAA0"`, while pinned GZDoom `src/r_data/sprites.cpp` documents four-character sprite families plus frame/rotation. The full archive texture loading path may alter actual behavior; **no missing sprite is proven**.

| Case | B0 unchanged observation (future) | Disposable B1 controlled variable | Non-negotiable oracle |
|---|---|---|---|
| SPR-B0 | original OreShard actor draws intended sprite, pickup works | none | render and actor interactions recorded |
| SPR-01 | same actor+state as B0 | change **one** sprite alias/name in a disposable copy | only intended visual linkage changes; actor logic invariant |
| SPR-02 | original locator actor/HUD state | change one locator alias in disposable copy | visuals isolated from class and DoomEdNum |
| SPR-03 | original altar `ELECA0` | remove/rebind one frame in fixture | missing frame detected, no uncontrolled class change |
| SPR-04 | original tool/sprite PNG lookup | one-variable sprite namespace test | no unrelated game archive mutation |

**Mutation constraint:** do not rename files inside authoritative `GhostMan612/Sovereign-Nodes`; change only an approved copy under exact allowed sandbox. Record each original/fixture member path, raw SHA-256, output PK3 hash, change type, patch digest, actor ID and visual observation.

**Do not conflate:** a long raw PNG filename, a literal ZScript `Sprite` value, a sprite-family resolver and GLDEFS `light.texture` association. These may have different validation paths. Capture B0 actual run before interpreting B1; `AUTH-F` authorizes creation only, `AUTH-T` authorizes any engine run separately.
