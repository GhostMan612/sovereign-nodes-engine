# F-01 — Immutable path, asset and privacy boundaries

## Canonical workspace partition

| Class | Allowed future role | Forbidden mutation |
|---|---|---|
| `C:\sovereign-nodes-engine` | operator-maintained planning docs and approved curated evidence | no game WADs, build caches, GPU trace dumps or private data |
| original `GhostMan612/Sovereign-Nodes` checkout | immutable source read/source hashes only | no fixture patches or source build in place |
| external candidate engine source (once separately approved) | checkout source at exact immutable SHA | no auto-update, code patch outside approved scope |
| designated disposable `F02` fixture sandbox | B1/B2 synthetic, bounded copy and rollback | no authentic IWAD in public repo; no symlink/junction escape |
| dedicated build folder | compiler cache and binaries for approved candidate | no shared CMake cache across forks/configs |
| operator-private results directory | full logs/raw GPU trace/evidence and signed decisions | never pushed or attached unredacted |

Paths in this document are *classes/examples*, **not authorized real local folders**. A future operator must choose exact absolute resolved paths. Do not follow symlinks/reparse points outside allowed roots, use broad `C:\` write allowance, recursively delete unknown folders or use `git clean -fdx` to recover.

## Mandatory data classification

- Allowed in public Markdown after review: immutable public source URL and SHA, synthetic-only sample identifiers, sanitized numeric metrics and checksum of raw evidence.
- Private/off-repo only: host/usernames, absolute home/temp paths, device serials, tester contact, signed approval proof, exact local license-installed game asset location, raw traces containing sensitive strings.
- Never use as test data without a separate specifically reviewed decision: genuine Mantle graph, genealogical names, vault, keys, credential stores, personal case records, untrusted Python mods or commercial IWAD binary bytes.

## Output whitelist

Every future authorization lists file pattern *and* exact root, size/retention policy, a sanitized summary path and hashes; no `outputs: anywhere`, generic wildcard write access or automatic upload. Stop if an allowed source unexpectedly resolves to private user information.
