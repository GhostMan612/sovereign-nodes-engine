# WO-F / F-01 — Operator authorization matrix and non-inheritance contract

**GLOBAL DEFAULT: NO AUTHORITY GRANTED.** This document and every unsigned template are specifications, not permission. User controls task selection and any dated approval outside this repository. Published Markdown is not a consent artifact.

| ID | Category | Required exact scope | Allowed only with separate authenticated operator approval | Never implied |
|---|---|---|---|---|
| AUTH-R | distinct-source review | reviewer identity private ref, immutable URLs/paths, read-only tools, time range | primary-source inspection and written dissent | repo/device mutation, independent G7 without real reviewer |
| AUTH-H | machine metadata | device, enumerated read-only commands, redacted output fields, location | inspection of existing versions and read-only package hashes | software install/driver change/build/game execution |
| AUTH-F | disposable fixture | immutable game base, synthetic payload, exact isolated paths, file limit and rollback | write within approved temporary fixture root | editing game `GhostMan612/Sovereign-Nodes`, release resources |
| AUTH-B | native build | exact candidate SHA, compiler/SDK/toolchain, pinned deps, dirs/network budget | approved build/configure commands on approved host | gameplay, benchmarks, system installs, arbitrary downloads |
| AUTH-T | gameplay/parity test | exact source/binary/PK3 SHA, lawful IWAD reference, C-series cases, session | approved bounded game session and log collection | raw private data, engine fixes or performance conclusions |
| AUTH-P | GPU benchmark | actual test device, acceptance thresholds, test matrix, time/stress caps | only protocol-defined capture after G3 readiness | indefinite stress, inferred FPS, overclock/driver changes |
| AUTH-S | security/rights research | records/sources, reviewer and no-private-data bounds, deliverable | source/dependency review; approved synthetic threat reasoning | native untrusted Python, exporting Mantle vault, distribution |
| AUTH-I | implementation | separate repair or Phase-01 work order, exact files, tests, signatures | only what future implementation approval states | permission from F-01 template, upstream PR |
| AUTH-D | distribution/upstream | signed SBOM, rights/asset/branding and project contribution review | distinct specifically approved release action | bundling IWAD or submitting AI-assisted UZDoom upstream PR |

## Mandatory authorization record

- Independent `authorization_id` and `scope_freeze_id`; one category only.
- `request_state=PROPOSED` until operator supplies a genuine privately verifiable dated authorization. `operator_signature_private_ref` is a reference, not a signature placed into public Git.
- Exact named actor, device, source Git repos and SHAs, allowed read and write path lists (never path wildcards), allowed task/command list, flags and dependency versions, output/evidence root, raw-data retention, network policy (default deny), time and maximum duration.
- Permitted asset references must be legal and external to the repo; no proprietary IWAD bytes, real genealogy, passwords, tokens, usernames, hostnames, local paths or reviewer personal contact in public records.
- Expiry, stop events, reversal of disposable changes and revocation reference; invalid, absent or expired consent always blocks execution.

## Approval lifecycle and trust

1. Draft an unapproved *request*. Review exact source and security boundaries.
2. Operator explicitly approves or rejects the specific request and its immutable scope digest using an independently confirmable channel.
3. At dispatch, the executing actor verifies operator identity/authority, scope, any earlier conflicts, expiry and current non-revocation. JSON `APPROVED` text alone is **insufficient**.
4. Perform only the separately approved work; collect sanitized evidence; log any stop/partial status honestly.
5. Stop immediately on revocation, expiration, source/hash/path mismatch, unapproved download, private-data risk or scope change. Changed scope requires **new approval ID**, not edit-in-place.
6. A completed action never authorizes another category; execution and review roles stay separate.

## This release's active grants

**NONE.** F-00 external review is still unsigned; F-01 only supplies documents and blank forms. `AUTH-I` and `AUTH-D` remain outside F-01 and require later independent operator decisions. `ADR-SNE-002` stays HOLD.
