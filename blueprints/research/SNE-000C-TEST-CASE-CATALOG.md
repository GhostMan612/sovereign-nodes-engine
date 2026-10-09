# SNE-WO-000C — Complete operator test-case catalog

**All cases:** SPECIFIED ONLY / NOT RUN. An authoritative PASS requires an exact authorized engine/game revision, resource hash, test log, observed gameplay and tester approval. The test workflow below is a *specification*, not an instruction to execute now. Do not run before approval. No repository code modifications are included.

## Test case structure

Each test uses the same format: Setup (including legal game data), action, pass oracle, control or negative case, failure conditions. For cross-engine runs, execute each case separately on GZDoom, UZDoom and BiasedDoom and attach independent evidence. ZDaemon has its own separate lane.

### C-001 — Custom-resource load

- **Setup:** Pinned lawful IWAD + owner-verified PK3; known GapNode marker.
- **Procedure:** Start engine with project PK3 and MAP01; inspect title and marker.
- **PASS oracle:** Gameplay uses exact custom GapNode and expected unique actor; script log has no missing fragment.
- **Control/negative:** Startup with omitted PK3 demonstrates detection of Entryway/default fallback.
- **FAIL or blocked:** A vanilla map appears; marker missing; ambiguous result.
- **Evidence:** record game SHA, engine SHA/binary hash, lawful IWAD reference/hash, PK3 hash, system and GPU driver, exact actions and logs; screenshots for visual changes; metrics for timed tests.
- **Result:** NOT RUN. **Operator signoff:** PENDING.

### C-002 — MAPINFO and fragments

- **Setup:** PK3 contains canonical MAPINFO and three .zs references.
- **Procedure:** Capture loader diagnostics and exercise class from each fragment.
- **PASS oracle:** All three fragments recognized; class/HUD/hand-off behavior demonstrates loading.
- **Control/negative:** In a disposable test fixture only, break one referenced fragment and confirm observable error.
- **FAIL or blocked:** Only compiled or files exist; fragment silently skipped.
- **Evidence:** record game SHA, engine SHA/binary hash, lawful IWAD reference/hash, PK3 hash, system and GPU driver, exact actions and logs; screenshots for visual changes; metrics for timed tests.
- **Result:** NOT RUN. **Operator signoff:** PENDING.

### C-003 — Three-map chain

- **Setup:** Deterministic fresh session and first-map start.
- **Procedure:** Use actual exits twice; record entered map names and interactive state.
- **PASS oracle:** MAP01→MAP02→MAP03 with correct map IDs; endpoint unambiguous.
- **Control/negative:** Missing MAP02/MAP03 test fixture aborts rather than false pass.
- **FAIL or blocked:** Wrong map, missing destination, no expected exit.
- **Evidence:** record game SHA, engine SHA/binary hash, lawful IWAD reference/hash, PK3 hash, system and GPU driver, exact actions and logs; screenshots for visual changes; metrics for timed tests.
- **Result:** NOT RUN. **Operator signoff:** PENDING.

### C-004 — Sprite and actor identity

- **Setup:** Synthetic game fixture of ore, locator, altar, weapon and ID list.
- **Procedure:** Capture HUD/object render and interact with each DoomEdNum.
- **PASS oracle:** Correct actor class and visible intended frame, pickup/fire/damage as designed.
- **Control/negative:** Explicitly inspect ORESHAA0 and TOOLAA0 rendering, not just archive names.
- **FAIL or blocked:** Invisible sprite, bad frame, unresolved class or thing number.
- **Evidence:** record game SHA, engine SHA/binary hash, lawful IWAD reference/hash, PK3 hash, system and GPU driver, exact actions and logs; screenshots for visual changes; metrics for timed tests.
- **Result:** NOT RUN. **Operator signoff:** PENDING.

### C-005 — GLDEFS binding

- **Setup:** Scene with each of ELEC/ORESHA/TOOLA actor frame in view.
- **Procedure:** Screenshot identical light-on/off scenes and renderer/backend.
- **PASS oracle:** Actor-attached pointlight visibly changes scene and moves with owning actor.
- **Control/negative:** Build fixture with binding omitted while definition stays present.
- **FAIL or blocked:** Definition exists but no emitted light, GLDEFS not loaded.
- **Evidence:** record game SHA, engine SHA/binary hash, lawful IWAD reference/hash, PK3 hash, system and GPU driver, exact actions and logs; screenshots for visual changes; metrics for timed tests.
- **Result:** NOT RUN. **Operator signoff:** PENDING.

### C-006 — Synthetic Godot handoff

- **Setup:** Synthetic-only runId, 42 seed, SAMPLE ANCESTOR A, version=1.
- **Procedure:** Godot writes temp handoff and launches FPS; inspect scoreboard and source.
- **PASS oracle:** RunId/seed/name seen consistently, absent handoff safe.
- **Control/negative:** Repeat with true/false `hasParadox` and stale/unknown-schema variants.
- **FAIL or blocked:** Receiver missing/wrong values, or silent fallback claimed PASS.
- **Evidence:** record game SHA, engine SHA/binary hash, lawful IWAD reference/hash, PK3 hash, system and GPU driver, exact actions and logs; screenshots for visual changes; metrics for timed tests.
- **Result:** NOT RUN. **Operator signoff:** PENDING.

### C-007 — HUD state

- **Setup:** Known ore 0, shard pickup, locator pickup, altar cost state.
- **Procedure:** Show before/after HUD/scoreboard and actual inventory object.
- **PASS oracle:** Display delta matches engine state and standalone no-handoff case clean.
- **Control/negative:** No pickup should not change counter; actor with failed tag caught.
- **FAIL or blocked:** Vanilla-only HUD or stale counters.
- **Evidence:** record game SHA, engine SHA/binary hash, lawful IWAD reference/hash, PK3 hash, system and GPU driver, exact actions and logs; screenshots for visual changes; metrics for timed tests.
- **Result:** NOT RUN. **Operator signoff:** PENDING.

### C-008 — WAD byte semantics

- **Setup:** Owner-approved local generator output and verified independent validator.
- **Procedure:** Parse generated WAD and then actually enter unique map.
- **PASS oracle:** Correct generated lumps and meaningful map interaction.
- **Control/negative:** Malformed fixture tests wrong offsets, missing starts, unusable exit.
- **FAIL or blocked:** Header-only parse reported as full gameplay PASS.
- **Evidence:** record game SHA, engine SHA/binary hash, lawful IWAD reference/hash, PK3 hash, system and GPU driver, exact actions and logs; screenshots for visual changes; metrics for timed tests.
- **Result:** NOT RUN. **Operator signoff:** PENDING.

### C-009 — Level/save continuity

- **Setup:** Stable starting inventory, synthetic handoff and expected flags.
- **Procedure:** Save/reload/map transition and optionally revisit; compare state table.
- **PASS oracle:** Explicit contract state preserved, missing state recorded; no cross-fork save compatibility assumption.
- **Control/negative:** Cold session reset versus load distinguishes expected reset.
- **FAIL or blocked:** Unexplained lost or duplicated progression data.
- **Evidence:** record game SHA, engine SHA/binary hash, lawful IWAD reference/hash, PK3 hash, system and GPU driver, exact actions and logs; screenshots for visual changes; metrics for timed tests.
- **Result:** NOT RUN. **Operator signoff:** PENDING.

### C-010 — Graphics backend

- **Setup:** Same map and settings, per-engine allowed APIs.
- **Procedure:** Record selected backend in engine diagnostics and visible rendering.
- **PASS oracle:** Actual requested backend or explicit safe fallback is proven.
- **Control/negative:** Intentionally unavailable backend must not silently misreport selection.
- **FAIL or blocked:** Backend inferred from settings UI only.
- **Evidence:** record game SHA, engine SHA/binary hash, lawful IWAD reference/hash, PK3 hash, system and GPU driver, exact actions and logs; screenshots for visual changes; metrics for timed tests.
- **Result:** NOT RUN. **Operator signoff:** PENDING.

### C-011 — Voxels and glTF

- **Setup:** Fixture-only voxel replacement mapped to known actor; optional BiasedDoom glTF.
- **Procedure:** Compare sprite and voxel/model under exact health, damage, collision, animation.
- **PASS oracle:** Model displays and collision/gameplay invariant; distinct glTF external and GLB paths.
- **Control/negative:** Malformed model and missing textures cause bounded, observable failure.
- **FAIL or blocked:** Visual model invisible, actor changes mechanics, load crash.
- **Evidence:** record game SHA, engine SHA/binary hash, lawful IWAD reference/hash, PK3 hash, system and GPU driver, exact actions and logs; screenshots for visual changes; metrics for timed tests.
- **Result:** NOT RUN. **Operator signoff:** PENDING.

### C-012 — Lights and performance

- **Setup:** Identical 720p scene, same actor model and light locations.
- **Procedure:** Measure 0,2,8,16 light counts across repeated runs.
- **PASS oracle:** Full frame-time capture including p95/p99 plus screenshots; controls held constant.
- **Control/negative:** All lights off is repeatable control; stress does not prevent recovery.
- **FAIL or blocked:** Invented GPU results or cross-setting comparison.
- **Evidence:** record game SHA, engine SHA/binary hash, lawful IWAD reference/hash, PK3 hash, system and GPU driver, exact actions and logs; screenshots for visual changes; metrics for timed tests.
- **Result:** NOT RUN. **Operator signoff:** PENDING.

### C-013 — Curated third-party mod scope

- **Setup:** Legal shareware/freeware packages and license record.
- **Procedure:** Load small named safe set as separate fixtures.
- **PASS oracle:** Feature support scope recorded per exact engine build.
- **Control/negative:** Unsupported requested mod reports error without corruption.
- **FAIL or blocked:** Claim of universal mod compatibility.
- **Evidence:** record game SHA, engine SHA/binary hash, lawful IWAD reference/hash, PK3 hash, system and GPU driver, exact actions and logs; screenshots for visual changes; metrics for timed tests.
- **Result:** NOT RUN. **Operator signoff:** PENDING.

### C-014 — ZDaemon separate lane

- **Setup:** Operator-installed ZDaemon and independently compatible content pack.
- **Procedure:** Test its real supported map/thing/multiplayer subset.
- **PASS oracle:** Explicit ZDaemon-only results; no modern-engine feature assumptions.
- **Control/negative:** GZDoom-only features are recorded N/A with reason.
- **FAIL or blocked:** GZDoom runtime used to claim ZDaemon parity.
- **Evidence:** record game SHA, engine SHA/binary hash, lawful IWAD reference/hash, PK3 hash, system and GPU driver, exact actions and logs; screenshots for visual changes; metrics for timed tests.
- **Result:** NOT RUN. **Operator signoff:** PENDING.

### C-015 — Handoff trust and malformed input

- **Setup:** Synthetic fixtures only, bounded temp paths.
- **Procedure:** Try missing file, stale runId, malformed JSON, bool, missing/newer schema.
- **PASS oracle:** Record actual current behavior; fail closed as future design requirement if spec demands.
- **Control/negative:** No private record/access; future-version tolerated must be labeled as such.
- **FAIL or blocked:** False security claim or private data in test artifacts.
- **Evidence:** record game SHA, engine SHA/binary hash, lawful IWAD reference/hash, PK3 hash, system and GPU driver, exact actions and logs; screenshots for visual changes; metrics for timed tests.
- **Result:** NOT RUN. **Operator signoff:** PENDING.

## Extended cases outside original C-001..015

| ID | Planned scope | Acceptance oracle | Status |
|---|---|---|---|
| W-001 | Map change | correct map identities, no silent fallback | NOT RUN |
| W-002 | Transition snapshot | explicitly versioned bounded state survives an intentional map change | NOT RUN |
| W-003 | Preload illusion | no frames of wrong map, no false multi-zone claim | NOT RUN |
| W-004 | True multi-zone | separate future ADR; no current candidate credited by default | DEFERRED |
| SEC-001 | Source-specific JSON boolean | `hasParadox: true` and `false` round-trip semantically | NOT RUN |
| SEC-002 | Source-specific schema | record tolerant present behavior; proposed strictness requires change | NOT RUN |
| SEC-003 | Python trust | unknown PK3 does not execute unsandboxed Python by default | NOT RUN |
| PERF-001 | UHD 620 on actual laptop | 3-run frame-time trace per agreed profile | NOT RUN |

## Result object (documentation schema)

A future test report shall include: `caseId`, `engineRevision`, `gameRevision`, `binaryHash`, `pk3Hash`, `iwadProvenanceHash`, `fixtureId`, `backend`, `settings`, `osGpuDriver`, `runOrder`, `steps`, `observations`, `links`, `result`, `reviewer`. Accepted `result`: `NOT_RUN`, `BLOCKED`, `PASS`, `FAIL`, `N_A_WITH_REASON`. Never insert personal genealogy or IWAD contents into results.
