# WO-F — Truthful evidence states and adjudication rules

## Controlled vocabulary

| State | Exact meaning | Permitted without a run? |
|---|---|---|
| `SOURCE-OBSERVED` | immutable pinned source text inspected | yes; not gameplay proof |
| `DOC-CLAIM` | upstream author documented behavior | yes; not independently verified |
| `TEST-SPECIFIED` | fixture, action, oracle, negative control are described | yes; no results |
| `NOT RUN` | no authorized attempt took place | yes; default |
| `BLOCKED` | permission/resource/tool/license prerequisite prevents attempt | yes, with cause |
| `UNVERIFIED` | incomplete or ambiguous observation | yes, with unknowns |
| `PASS` | authorized run, expected observations, negative controls and signed evidence | **no** |
| `FAIL` | authorized run materially violates oracle, evidence retained | **no** |
| `INCONCLUSIVE` | authorized attempt lacked reliable evidence or fairness | **no** |
| `ACCEPTED` | operator signs reviewed documentation/gate, scope explicit | **never inferred** |

## Mandatory per-run identity

`work_order_id`, case ID, candidate name, source SHA, engine binary SHA-256, resource PK3 SHA-256, game source SHA, lawful IWAD external reference/hash, Windows OS/driver/toolchain, build flags, profile, relevant steps and negative control, log/trace checksum, tester and date, independent review outcome. Redact private system paths and identifiers from public summaries.

## Invalid proof examples

- Engine boots vanilla Entryway → `FAIL C-001`, not a benchmark.
- Source code references a GLDEFS light → `SOURCE-OBSERVED`, not illumination `PASS`.
- Build README advertises glTF → `DOC-CLAIM`, not compiled model `PASS`.
- No lawful IWAD available → `BLOCKED`, not a failed engine.
- Modified fixture passes but unchanged game fails → fixture finding, unchanged-game case remains `FAIL`/`UNVERIFIED`.
- A reviewer approves the document language → documentation accepted only; G3–G5 are still `NOT RUN`.
- Reviewer and author are identical → G7 remains `BLOCKED`.

## Promotion control

A result becomes `PASS` only after an independent reviewer validates test setup, actual artifact identities, controls and absence of contradictory evidence. A hard dependency missing yields HOLD. Operator signs individual gates, then separately the ADR.
