# WO-F — Immutable baseline and cross-candidate experiment identity

## Locked historical source pins (verify again before any future run)

| Material | SHA | Classification |
|---|---|---|
| SNE planning repository | `1644fb80c3e2803dd19465292423832e8fdf8e24` | WO-F extraction preimage |
| Source game | `44034e97fd22129f919a18cadceb84466ef1bcd3` | source-only game baseline |
| GZDoom | `c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7` | proposed control source |
| UZDoom | `dbedcc894fb6866c48520cf27ae773f9957024b9` | separate comparator source |
| BiasedDoom | `6147e0670458e48e63d1a40750f36dfc68b00f7f` | experimental candidate source |

These are **research pins**, not a verified installed executable, upstream latest version or chosen release. If the operator selects different source commits for actual tests, add a new immutable identity record and disclose divergence; never silently rewrite historical ledgers.

## Test artifact identity (future fields, all currently unknown)

- Path/hash of exact original unmodified PK3 built by canonical game tooling: `UNKNOWN`.
- Hash and legal provenance of external official IWAD, stored outside repository: `UNKNOWN`.
- Engine binary/config/resource PK3 hashes per candidate and build: `UNKNOWN`.
- Windows/MSVC/SDK/graphics driver versions and actual renderer backend: `UNKNOWN`.
- Deterministic test seed and `GapNode` unique marker that cannot be mistaken for `Entryway`: `TO DEFINE`.
- Independent resource-package audit: `NOT RUN`.

## Rules for comparability

1. Hold identical game PK3 bytes/hash across GZDoom and UZDoom parity testing. If incompatible syntax requires adaptation, record a separate adaptation experiment, never call it *unmodified* parity.
2. Each per-engine run records its own source/binary/resource package and renderer choices; a successful control run does not certify other engines.
3. For a negative control, omit **only a disposable copied** project PK3; never modify licensed IWAD or canonical game source. Confirm the expected unique marker is absent.
4. A map title alone may be spoofed; prove map geometry and one unique project actor/interact as well as `GapNode` title.
5. Do not include source/game binaries, WADs, logs with sensitive paths, or unredacted machine details in this ZIP or the public repo.

## Admission criteria

Without a known legitimate IWAD, exact original PK3 hash and demonstrably correct `MAP01`, all C-series parity and performance comparisons must stay BLOCKED or NOT RUN.
