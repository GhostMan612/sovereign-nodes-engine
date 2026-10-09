# SNE-WO-000D — Blank evidence templates

The JSON documents here are **blank schema examples**, not results. Values of `null` mean unknown/unrecorded; `NOT_RUN` is an explicit workflow status and never `PASS`. Do not fill real secrets, names, private paths, genealogy or unlicensed content. For any future operator run, create separate local copies and record the actual SHA-256 identities for engine binary, support resources, game package, original lawful IWAD, raw capture and full environment.

| Template | Future producer | Use |
|---|---|---|
| `SNE-000D-HARDWARE-RECORD.json` | laptop operator | immutable OS/GPU/driver/toolchain/power snapshot |
| `SNE-000D-BUILD-RECORD.json` | laptop operator | one actual candidate/configure/build lane |
| `SNE-000D-RUN-RECORD.json` | laptop operator | one complete trial with frame-time data provenance |
| `SNE-000D-DEPENDENCY-RECORD.json` | independent dep reviewer | one library/component and its license provenance |
| `SNE-000D-REVIEW-RECORD.json` | independent reviewer | defect and acceptance state without fabricated test PASS |

No JSON instance implies a populated schema or successful validation. Every future record needs reviewer name/role and date before formal acceptance; use consented non-sensitive aliases in public copies.
