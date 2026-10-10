# F-02 — Immutable identity fields, hashing and cross-run correlation

| Entity | Historical pin or future required field | Current validity |
|---|---|---|
| SNE planning document | `725fded39c0d50139ab76182211e32375bc2764e` | verified published Git commit |
| Source game | `44034e97fd22129f919a18cadceb84466ef1bcd3` | immutable source text, not package result |
| GZDoom control | `c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7` | source pin only |
| UZDoom comparator | `dbedcc894fb6866c48520cf27ae773f9957024b9` | source pin only |
| BiasedDoom experimental | `6147e0670458e48e63d1a40750f36dfc68b00f7f` | source pin only |
| Unmodified B0 PK3 | SHA-256 of actual bytes + size + canonical build input manifest | **UNKNOWN** |
| MAP01–03 generated WADs | SHA-256 each, byte-size, directory count, independent parse | **UNKNOWN** |
| Lawfully held external IWAD | SHA-256 + rights reference private, no binary added | **UNKNOWN** |
| Candidate engine | source Git SHA + binary SHA-256 + resource hash + flags | **NOT BUILT** |
| Windows host | device alias + OS build, GPU/driver, compiler/SDK, redacted capture hashes | **NOT INVENTORIED** |

## Hash discipline (proposed once approved)

Compute raw file-byte SHA-256, not the `git blob` SHA-1 used to guard tracked document replacement. Keep raw sha256, file size and UTC capture time together; fingerprint each fixture independently. Fingerprints are **not** asset distribution rights.

For a binary copy control, compare B0 input and B0 staged copy hashes before and after any future run. Mutated B1/B2 must never reuse B0 identity. Record `sha256` of synthetic JSON as raw bytes and any normalization explicitly. Do not use output filename alone to infer contents.

## Scope changes

New source revision or modified fixture ⇒ new identity record and new explicit authorization if scope changes; historical SHA rows never silently updated. No actual checksum has been collected by this package.
