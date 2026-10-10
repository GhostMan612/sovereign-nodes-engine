# F-01 — Scope freeze protocol and baseline guard

## Freeze before operator approval

One request must specify **exactly one** category from `AUTH-R/H/F/B/T/P/S/I/D`, along with its task ID, named/privately referenced actor, objective, pinned planning base, immutable upstream SHA(s), source read list, permitted write roots, authorized commands/methods, permitted inputs, network/dependency budget, maximum duration, output/evidence root, retention and stop/rollback. Blanket approval, relative root, `*`, `..`, unbounded shell, dynamic ref `main`, symlink/junction traversal or global temp-folder access are invalid.

## Permission record states

- `PROPOSED` — author draft, no authority.
- `APPROVED` — only after operator authenticates the exact frozen record and private signature, and all local context fields match; textual assertion alone insufficient.
- `DENIED` — do not execute.
- `REVOKED` — stop and preserve safe records, no new work.
- `EXPIRED` — temporal validity elapsed; new approval needed.
- `COMPLETED` — future task concluded; no extension to other work.

## Freeze digest

A future controller may canonicalize the complete scope JSON with deterministic UTF-8 serialization and compute SHA-256. Both operator and executing actor must refer to the **same digest** before any activity. Record the method: keys sorted lexicographically, no insignificant whitespace, UTF-8 encoded; exclude the digest itself and signature metadata from the hashed immutable `scope` object. Any change to paths, flags, actor, source SHA, network policy or time requires **new authorization ID** and re-signoff. This overlay supplies the schema and blank scope object only, no actual digest.

## Preflight sequence for a later *approved* task

1. Confirm operator identity/signature outside public Git, authorized action, no revoked/expired state and exact source SHA.
2. Verify machine/repo clean baseline and that source/target directories exist and are not aliases escaping the approved path roots.
3. Check lawful resource provenance, license notices and all specifically prohibited operations before any dependency retrieval.
4. Capture a redacted pre-execution inventory and proposed side-effect list; if larger than approved budget, return HOLD.
5. Execute bounded task only under a distinct future work order and preserve case evidence; record exit reason and scope digest.

**No local preflight is run by F-01.** Planning repository baseline for ZIP installation is `148dc28cdbdf4970c8011d76762b31b8dcafea0b`, not an engine source checkout.
