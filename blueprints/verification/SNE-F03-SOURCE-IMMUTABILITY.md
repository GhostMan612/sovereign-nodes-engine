# F-03 — Candidate source immutability and freeze

| Candidate | Pinned source SHA | Lane |
|---|---|---|
| GZDoom | `c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7` | first diagnostic control |
| UZDoom | `dbedcc894fb6866c48520cf27ae773f9957024b9` | distinct production-comparator test lane |
| BiasedDoom | `6147e0670458e48e63d1a40750f36dfc68b00f7f` | experimental, gated independently |

## Future authorized source inspection

- Verify immutable origin URL, exact commit, clean checkout, staged/untracked changes and source archive provenance; submodule/module pointers at that commit, including recursive state when relevant.
- Capture CMakeLists blob SHA and relevant manifest/version file blobs to distinguish the *text* being configured from the actual configured tree.
- Do not `git pull`, switch tracking branch, add patch to engine tree or resolve dependencies from floating `main` during a trial. A new commit requires a new source identity and scope approval.
- If the repo already contains modifications, record and **STOP**; use a new approved isolated checkout rather than reset, clean, or discard operator work.
- Compare source commit to executable hash only after actual build. Source SHA cannot substitute for produced EXE and resource package SHA.

## Source-only checks already performed by package author

GZDoom root CMake at historical SHA specifies C++17. UZDoom root CMake specifies C++20 plus Python3 >=3.6 build-time, `FORCE_NO_LTO` and optional updater. BiasedDoom CMake specifies C++17, default ON glTF and Python flags. These facts are independently recheckable and **not build outcomes**. See `evidence/sources/SNE-F03-CMAKE-OBSERVATIONS.md`.
