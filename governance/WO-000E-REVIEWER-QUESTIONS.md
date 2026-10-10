# WO-E — Questions an independent reviewer must not evade

1. Can you demonstrate one actual build and runtime of custom GapNode rather than a vanilla IWAD map? If not, what exact evidence is missing?
2. Does the existing PK3 use real sprite four-letter names and rotations? Can you point to the engine parser and actual packaging names?
3. What happens when the handoff contains `hasParadox: true`, `false`, absent, stale or malformed? Does behavior reflect original game rather than the proposed fix?
4. Are all three MAPINFO ZScript fragments compiled, instantiated and observable? Does one pass on GZDoom imply any pass elsewhere?
5. Are lights attached to an actor frame, or merely declared in GLDEFS? How do you detect a missed binding without trusting screenshots alone?
6. Does BiasedDoom GLTF ON build, animate and texture both external `.gltf` and embedded `.glb`? Is Python disabled or unsandboxed?
7. Which source licenses/asset rights are still missing? What changes if binaries rather than source-only documentation are distributed?
8. Can UZDoom GPL downstream rights and no-AI upstream PR rules be distinguished without treating either as irrelevant?
9. Why does the review suggest GZDoom control-first, and what would falsify that preference?
10. What frame-time evidence on the actual UHD 620 exists? Is mean FPS masking stutter, missing lights or mismatched scenes?
11. Can inherited hub machinery provide W1/W2 without pretending true multi-zone W4 streaming?
12. Who maintains downstream modifications, reviews future upstream changes and authorizes rollback? What if all candidates fail?
13. Has a distinct reviewer reproduced any claim independent of the author? Where is the dissent log?
14. Does documentation publication improperly mark earlier work orders accepted? How are acceptance records handled?
15. Is Phase 01 prevented until separate explicit owner authorization even if this document is signed?

Answers must point to immutable source or authorized real run evidence. The accurate answer 'NOT RUN / UNKNOWN' is preferable to unsupported confidence.
