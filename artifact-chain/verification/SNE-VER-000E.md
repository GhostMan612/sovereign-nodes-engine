# SNE-VER-000E — Verification protocol and actual scope

## Overlay package checks

| ID | Expected validation | Status from package author |
|---|---|---|
| V-E01 | ZIP central directory and CRC; exactly declared members | archive generator will record final check |
| V-E02 | only Markdown/JSON; no path traversal, `.git`, script, binary or IWAD | archive generator will record final check |
| V-E03 | UTF-8, LF, terminal newline, no trailing whitespace | archive generator will record final check |
| V-E04 | JSON syntax and SHA-256 uncompressed-member digest except self ledger | archive generator will record final check |
| V-E05 | eight REPLACE paths match immutable parent Git blob preimages | checked by source inspection; operator verifies own HEAD before extract |
| V-E06 | counts and actions agree with `WO-000E-MANIFEST.md` | archive generator will record final check |

The machine-generated `scaffold/WO-000E-BUILD-VERIFICATION.json` records **ZIP validation only**. It is not a Windows engine build, QA test, security audit or independent reviewer.

## Acceptance gates outside package

- C-001…C-015: **NOT RUN**.
- Native Windows GZDoom/UZDoom/BiasedDoom builds: **NOT RUN**.
- UHD 620 frame-time traces and performance: **NOT RUN**.
- Complete legal/SBOM and Mantle threat control: **NOT CLEARED**.
- Independent reviewer: **PENDING**.
- Operator selection and Phase 01: **NOT AUTHORIZED**.

## Operator local install/check

Verify clean baseline before extracting, then `git status --short`, `git diff --check`, `git diff --stat`; stage **exact 48 paths**; `git diff --cached --check` and name-only inventory; commit/push only manually after the operator verifies. A clean staged check has no output; LF→CRLF notices under Windows are not whitespace errors.
