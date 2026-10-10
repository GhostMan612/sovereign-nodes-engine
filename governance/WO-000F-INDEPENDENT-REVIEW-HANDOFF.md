# WO-F — Independent verification reviewer assignment packet

## Reviewer appointment

An independent reviewer is a distinct qualified person/team that checks primary source and actual run evidence. The package author cannot be the independent reviewer. If no reviewer is available, record `P00-G7: BLOCKED` and keep ADR HOLD. A different AI assistant summarizing the same claims without source/runs independently inspected is not sufficient proof of independence.

## Ordered review questions

1. Do the precise source pins/paths/visible blob SHA values correspond to the claims? Audit sprite lookup, game frame aliases, producer/consumer `hasParadox`, and `validate_pk3.py` missing-path issue first.
2. Is the official source game unmodified during each parity result? Does a unique GapNode marker distinguish Entryway, including no-PK3 negative control?
3. Are B0(original) and B1/B2 fixture hashes distinct, modifications minimal, and resulting classes accurately attributed to game-versus-engine?
4. Are Windows MSVC/CMake configuration/source dependencies and candidate hashes traceable, with optional BiasedDoom Python/glTF and UZDoom LTO/updater flags controlled?
5. Is device performance based on real UHD 620 frame traces with lighting/model fidelity and thermal/cap confounds documented?
6. Are commercial assets, brand marks, bundled libraries, GPL source/notice obligations and upstream contribution policy independently adjudicated?
7. Are temp-file security, synthetic-only Mantle separation, untrusted CPython and world persistence limitations independently challenged?
8. Does the ADR scorecard remain null where evidence is absent? Is the reviewer explicitly separate from research author? Are dissent and operator decisions preserved?

## Reviewer deliverable (future)

For each observation record claimed text/runs, reproduced source links, decision `SUPPORTED/REJECTED/UNRESOLVED`, severity, correction, evidence pointers, remaining conflicts and date. Use blank `templates/SNE-000F-REVIEW-RESULT.json`. Personal reviewer identity/contact may be kept in private signed record; use an assigned non-identifying reviewer ID in public repo.

## Critical defects requiring escalation

Source claims incorrect, fixture-only repair passed as original parity, missing legal WAD, ambiguous game identity, fake FPS/binary/log hashes, fabricated independent signoff, any sensitive-data leak. `G7` and `G8` remain open until independently reviewed and operator signs actual gated results.
