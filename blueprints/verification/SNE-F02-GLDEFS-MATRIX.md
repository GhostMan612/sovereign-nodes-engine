# F-02B — GLDEFS definitions, associations and visible-light controls

## Pinned source observations

`game/GLDEFS.txt` declares `pointlight ELEC`, `ORESHA`, `TOOLA` and matching `light` blocks whose `texture` names are `ELECA0`, `ORESHAA0`, `TOOLAA0`, respectively. `build_pk3.py` places `GLDEFS` at PK3 root. **This proves text exists, not a light emits.**

| Case | Test-only proposed contrast | Actual oracle after AUTH-T |
|---|---|---|
| L-01 | identical B0 actor and scene with dynamic lights feature enabled vs disabled | visible, actor-tied light delta, screenshot and renderer/backend captured |
| L-02 | disposable B1 copy omits one *binding*, keeps pointlight block | specific actor-bound emission disappears without unrelated scene changes |
| L-03 | disposable B1 copy modifies only `texture` association | any effect localized and recoverable; collision/actor semantics unchanged |
| L-04 | control GLDEFS disabled or omitted in disposable PK3 | no silent fallback misclassified as valid binding |
| L-05 | one candidate vs another, exact same B0 PK3 SHA | isolate parser differences and true resolved textures |

Original B0 remains unchanged and separately scored. To claim effect on UHD 620, first prove correct scene and identity; lighting stress counts (0/2/8/16) are F-05 *later* and require AUTH-P, not implied by this test plan. No actual light or frame-time test has run.
