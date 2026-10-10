# F-01 — Proposed `AUTH-F` synthetic fixture preparation

**STATE: NOT AUTHORIZED.** The source game at `44034e97fd22129f919a18cadceb84466ef1bcd3` is *read-only*. No fixture is actually created by this package.

## Three-resource partition

- **B0 original:** immutable upstream source ref and a future checksum-identified canonically packaged PK3; never modified or relabeled after repair.
- **B1 controlled sprite:** generated/test-only copy changing exactly one sprite name, alias or GLDEFS binding to isolate ORESHAA0 and TOOLAA0; its own content and PK3 hash.
- **B2 controlled handoff:** synthetic-only JSON with true/false versus numeric variants, schema/malformed/replay cases, new runId and no real names; input hashes distinct from B0.

## Scope freeze requirements

Specific isolated workspace outside `sovereign-nodes-engine` and original `Sovereign-Nodes`; absolute canonical path; no junction/symlink crossing; allowed input files, output count/size, fixture generator source pin, synthetic payload identifiers, deterministic mutations, cleanup/retention and rejection controls. A SHA-256 copy/diff manifest records every changed input/output. No commercial IWAD copied into ZIP/public Git.

## Execution boundary

Creating a fixture needs `AUTH-F`; **launching an engine with it** also needs separately approved `AUTH-T`, and any build needs `AUTH-B`. `AUTH-F` never permits patching the authoritative game files or assuming an altered fixture passing validates B0. If the canonical repo or asset directory would be touched, STOP and request a different scope.
