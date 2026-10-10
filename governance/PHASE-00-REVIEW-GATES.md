# SNE-P00 — Technical acceptance and F-02 authorization gates (v1.1.0)

**Documentation published through F-01 `725fded39c0d50139ab76182211e32375bc2764e`; F-02 is a proposal to verify baseline identities, not a completed run.** Git publication, author review, independent review, test execution and operator acceptance are distinct.

| Gate | Evidence to close | Current state | F-02 contribution |
|---|---|---|---|
| P00-G1 | immutable source/text claims rechecked by distinct reviewer | AUTHOR RECHECK; INDEPENDENT PENDING | exact pins, validator/SNDINFO source triage |
| P00-G2 | transitive code, asset/brand/IWAD legal rights | NOT CLEARED | future privately logged lawful resource refs only |
| P00-G3 | C-001..C-008 on actual unchanged PK3 with negative controls per candidate | NOT RUN | original B0 hash and future GapNode falsification |
| P00-G4 | reproducible native Windows binary/resource SHA and toolchain | NOT RUN | future read-only host inventory only |
| P00-G5 | ≥3 actual UHD 620 frame traces, preagreed thresholds and comparable visible scenes | NOT RUN | nothing measured here |
| P00-G6 | synthetic bool/malformed/stale handoff and embedded Python/Mantle safety | NOT RUN | future B2 controls, no real data |
| P00-G7 | qualified reviewer distinct from author, documented dissent | NOT COMPLETE | source-review handoff only |
| P00-G8 | operator signed foundation, accepted tradeoffs, rollback + separate Phase01 authorization | HOLD | no selection |

## Non-inheriting categories

- `AUTH-R`: separate source reviewer; `AUTH-H`: read-only metadata and specifically enumerated lawful file hashes.
- `AUTH-F`: write disposable synthetic/altered fixture in scoped sandbox; `AUTH-T`: any engine/game runtime. Both needed where preparation plus actual launch occur.
- `AUTH-B`: native candidate engine build; `AUTH-P`: UHD frame-time capture; `AUTH-S`: security/licensing review; `AUTH-I`: implementation; `AUTH-D`: distribution.
- **All unsigned and unapproved** at package release. A published JSON with state `APPROVED` is not private authenticated consent. Every category needs exact actor, paths, source revision, permissible operations, timeframe, resource rights, stop/rollback and revocation verification.

## Correctness stops

- Missing original PK3/IWAD provenance, no unique GapNode project actor, unknown binary identity, invalid negative control, or fixture alteration being presented as unchanged-game PASS ⇒ HOLD or FAIL only with actual evidence.
- Pinned builder intentionally **excludes SNDINFO**. Marking absent SNDINFO as a package defect without checking exact builder revision is invalid.
- If device, path or Git preimage differs from signed scope/manifest, stop—not a request to install a dependency or patch source.
- Reviewer author cannot self-approve G1/G7; legal and private-data obligations are separate.

`ADR-SNE-002` continues **HOLD**. A completed F-02 blueprint has no independent authority to close G1…G8.
