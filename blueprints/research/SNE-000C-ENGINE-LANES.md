# SNE-WO-000C — Candidate compatibility lanes

## Candidate tests are distinct experiments

| Lane | Engine revision | Main hypothesis | Blocking proof required | Non-transferable result |
|---|---|---|---|---|
| GZ | `c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7` | first production parity baseline given current 4.14 game | custom PK3, script classes, GLDEFS, handoff, map chain | GZ results cannot certify UZ or BD |
| UZ | `dbedcc894fb6866c48520cf27ae773f9957024b9` | comparable inherited code with C++20/toolchain differences | independent build, gameplay + driver + licensing/policy | UZ code PR policy distinct from local fork rights |
| BD | `6147e0670458e48e63d1a40750f36dfc68b00f7f` | experimental modern glTF, Python and postFX surface | same Tier-A baseline **before** testing model bells/whistles | README glTF support not compile/runtime confirmation |
| ZDaemon | operator's future pinned version | separately authored compatibility subset | native server/client+map behavior proof | modern ZScript/PBR/GLDEFS cannot be assumed |

## Promotion rules

1. Production candidate must satisfy all **C-001 through C-008** blockers. C-009..C-015 include high/medium issues that cannot be waived without independent review and explicit operator decision; licensing and security gate are hard blockers even if a visual demo works.
2. Score rubric remains unfilled until results exist; **no invented weighted scores**.
3. Compare all candidates against exactly the same packaged game binary hash, IWAD provenance and synthetic fixtures; if an engine requires a modified game, record the adaptation cost explicitly, not as effortless parity.
4. Avoid maintaining multiple unrelated renderer forks before gameplay source compatibility is proven.
5. Assess BiasedDoom's longer-term stated ZScript deprecation intent against the source game's heavy ZScript requirements, while recognizing current documented support has not disappeared.

## Security and legal reminders

UZDoom upstream CONTRIBUTING disallows AI-assisted code submissions; this is not automatically a license prohibition on independently maintained GPL-compatible forks. Confirm actual downstream license obligations and asset rights before redistribution. BiasedDoom CPython author docs expressly say script execution is unsandboxed: keep opt-in trusted-only.

Related: `CANDIDATE-MATRIX.md` (unscored) and `SNE-000C-TEST-CASE-CATALOG.md`.
