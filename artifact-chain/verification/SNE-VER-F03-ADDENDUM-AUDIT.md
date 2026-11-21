# SNE-VER-F03 Addendum — Independent documentary audit (DRAFT)

- State: **DRAFT / OPERATOR REVIEW PENDING / ACCEPTS NOTHING / PROMOTES NO GATE**
- Audit target: `main` @ `47d05ab` (== `origin/main`, clean tree), chain through SNE-WO-F03.
- Relationship: addendum to `artifact-chain/verification/SNE-VER-F03.md` under
  `artifact-chain/work-orders/SNE-WO-F03.md`. No existing artifact is modified,
  superseded or re-IDed by this document. Artifact IDs stay immutable.
- Author role: independent read-only auditor (Hermes Agent). Builder/reviewer/
  operator roles remain distinct and are not claimed here.
- Date: 2026-11-21. Authorization categories AUTH-R/H/F/B/T/P/S/I/D: not
  requested, not granted, not implied. No device, network, build or repo mutation.

## Scope

Documentary integrity of the published chain only: checksum ledgers, parent
pins, preimage pins, manifest-vs-commit agreement, reference integrity, and
honesty of stated states. Upstream source repositories, ZIP archives, host
hardware and runtime behavior are **out of scope / UNVERIFIED**.

## Method (commands reproducible)

1. Sync: `git fetch origin && git pull --ff-only` → already up to date, clean.
2. Delivery commits: `git log --diff-filter=A --format=%H -- scaffold/<ledger>`.
3. Member bytes at delivery: `git cat-file --batch` on `<delivery>:<path>`;
   SHA-256 compared in three variants: raw, LF-normalized, rstrip-spaces-per-line.
   Host has `core.autocrlf=true`; working-tree bytes are not trustworthy.
4. Parent pins: each ledger's parent field == `git rev-parse <delivery>^`.
5. Preimage pins: `git rev-parse <parent>:<path>` vs pinned blob SHA-1.
6. Diff audit: `git diff --name-status <parent> <delivery>` vs manifest ADD/REPLACE sets.
7. Hygiene/encoding/links: blob scans for CR bytes, trailing whitespace, UTF-8
   strict decode; reference resolution by path, then basename index.
8. All 55 JSON files parsed strictly.

## Gate results

| Gate | Observed | Exit |
|---|---|---|
| Remote sync | already up to date; clean tree | PASS |
| JSON well-formedness | 55/55 parse | PASS |
| Ledger hash chain | 457/474 entries byte-exact at delivery commit; all 17 exceptions fall in documented classes (self-exclusion, WO-000A publication-time whitespace normalization, historical snapshots) | PASS |
| Parent-commit chain | 11/11 declared parents match actual parent | PASS |
| Manifest vs commit diff | 12/12 exact ADD/REPLACE sets; zero out-of-manifest or deleted files | PASS |
| Replacement preimage pins | 61/61 ledger-level pins match; F-01 manifest table 2/5 (see F1) | FAIL (F-01 only) |
| Blob hygiene | CRLF 0; UTF-8 errors 0; trailing whitespace 3 files | PARTIAL |
| Reference integrity | 731 refs resolve; 123 basename-only; 7 external-looking refs written repo-relative; 35 refs to 11 distinct bare external filenames | PARTIAL |
| Registry currency | F-03 publication SHA recorded as unknown though `47d05ab` exists; `registry/ARTIFACT-INDEX.md` lists no work orders | PARTIAL |
| Root README | byte-identical duplicate of `verification/README.md` | FAIL |
| Git attribution | single placeholder identity (`sovereign@example.com`) for all 12 commits; roles indistinguishable in history | PARTIAL |

## Findings

### F1 (HIGH) — SNE-F01 manifest preimage table contradicts its declared parent

Declared parent `148dc28cdbdf4970c8011d76762b31b8dcafea0b` (F-00 HEAD). Three of
five REPLACE pins match the older `1c01d2f` (WO-000F) state instead:

| Path | Manifest pin | Blob at `148dc28` | Pin true at |
|---|---|---|---|
| `blueprints/phases/PHASE-00-FOUNDATION.md` | `d2cfa6828f8a7be92b700042e38f942610647f4a` | `bca83a2f4e…` | `1c01d2f` |
| `blueprints/research/RESEARCH-QUEUE.md` | `14e4187a3320f4d77a70c70796584b4be3d8ae0ea2` | `6061509859…` | `1c01d2f` |
| `governance/PHASE-00-REVIEW-GATES.md` | `84c299f6db19197bbc5c1f7a38eb39b8121a1d58` | `61905f1862…` | `1c01d2f` |

The other two pins (`governance/WO-000F-AUTHORIZATION-MATRIX.md`,
`registry/PHASE-00-ARTIFACT-INDEX.md`) were correctly refreshed for F-00.
Inference (UNVERIFIED): the manifest was authored against the WO-000F state and
three pins were not re-baselined after F-00 republished those files. Consequence:
a clean checkout at the declared parent fails the package's own STOP guard.
Ledger member hashes still verify, so this is a guard defect, not corruption.
Remedy proposal: append provenance to F-01's reconciliation, never edit the
historical manifest; do not re-pin silently.

### F2 (MEDIUM) — Root front door missing

`README.md` is the identical blob of `verification/README.md` ("# Verification
workspace"). Repository root shows the wrong document to any newcomer.

### F3 (MEDIUM) — PHASE-00 ledger action misclassification

`scaffold/PHASE-00-FILE-SHA256.json` marks
`blueprints/research/RESEARCH-QUEUE.md` as `ADD`, but the file existed at base
`851452c` and was modified (`M`) by delivery commit `317e360`. Content hash is
correct; the ADD/REPLACE classification — the field that protects operator-local
files from silent overwrite — is wrong.

### F4 (LOW/MEDIUM) — Registry drift

`registry/PHASE-00-ARTIFACT-INDEX.md` records F-03 as "future Git SHA unknown"
though F-03 is published at `47d05ab` (REC-F03 deferred this explicitly; debt is
now stale). `registry/ARTIFACT-INDEX.md` has three rows and mentions no work order.

### F5 (LOW) — Trailing whitespace

`PHASE-00-INSTALL.md` (3 lines), `artifact-chain/evidence/SNE-EVD-000.md` (2),
`verification/PHASE-00-VERIFICATION-PLAN.md` (2). Contradicts the packages'
stated "no trailing whitespace" QA claim if read repo-wide. CRLF/UTF-8 clean.

### F6 (LOW) — Reference hygiene

123 references are bare basenames resolvable only by search; 7 are written
repo-relative but target upstream/external repos (`docs/scripting/python.md` ×4,
`docs/engine/procedural-map-generation.md` ×2, `SovereignNodes/fps_handoff.json`);
35 references use 11 distinct bare external filenames (`CONTRIBUTING.md` ×14,
`vcpkg.json` ×11) without repository qualification. `SNE-000D-RESULT-REVIEW.md`
is an intentional future-artifact reference, not a break.

### F7 (INFO) — Schema churn and attribution

Twelve packages use twelve distinct ledger schemas (member keys
items/files/entries/members; action vs operation; bytes/size_bytes/byte_length;
seven different parent-pin names). No canonical schema or in-repo validator
exists, so every audit is bespoke. Git history carries one placeholder identity
for author, operator and reviewer roles, which the chain contract requires to be
distinct.

## Verified observations vs pending / assumed

Verified: sync state; all 55 JSON parses; 457/474 ledger entries byte-exact at
their delivery commits; 11/11 declared parents; 12/12 manifest/diff agreement;
61/61 ledger-level preimage pins; hygiene and link counts above.

Pending / UNVERIFIED (do not read as PASS):

- The 5 entries in `scaffold/WO-000A-COMMITTED-SHA256.json` not matching its
  delivery commit coincide exactly with files republished by WO-000B; they are
  expected to match at its recorded `published_commit` `369722f`, but that
  re-hash was not performed in this pass. UNVERIFIED.
- Mapping of `PHASE-00-FILE-SHA256.json` base string "SNE-SCAFFOLD-0001 v0.1.0"
  to a concrete commit. UNVERIFIED (likely `851452c`).
- Cause attribution for F1 (stale pins vs wrong parent) is inference, marked
  UNVERIFIED.
- The ZIP archives, upstream source trees, host toolchain and every runtime
  state (all still NOT RUN per EVD/VER/ACC/REC) — UNVERIFIED, out of scope.

## Risks and rollback

- This addendum is documentation only. Risk: none to engine state; it creates no
  acceptance, no gate promotion, no authorization.
- Rollback: delete this file. No commits were made, no history rewritten, no
  remote touched, no existing artifact edited.
- Standing risks unchanged: ADR-SNE-002 HOLD; no AUTH-H inventory; no build lane.

## Next gated step (proposal)

Operator-signed `AUTH-H` read-only host/toolchain inventory per
`docs/SNE-F03-START-HERE.md` and `governance/SNE-F03-AUTHORIZATION-REQUEST.md`.
Every other gate waits on real host data; this document does not request or
grant it.
