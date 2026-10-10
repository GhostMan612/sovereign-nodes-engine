# F-03 — Frozen source and original documentation references

**Mode:** author read-only GitHub source inspection; no local host access, install, build or independent signoff. Historical source pins used:

| Material | Exact immutable Git SHA | Role |
|---|---|---|
| SNE planning | `f2f2cfec676b9a5254fa2a5a7e6f08198581fa09` | installation/preimage guard |
| Original Sovereign-Nodes game | `44034e97fd22129f919a18cadceb84466ef1bcd3` | unchanged game source and later runtime content provenance |
| GZDoom | `c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7` | proposed first control, not foundation |
| UZDoom | `dbedcc894fb6866c48520cf27ae773f9957024b9` | separate comparator |
| BiasedDoom | `6147e0670458e48e63d1a40750f36dfc68b00f7f` | experimental reference |

## Source primary blobs inspected

| Repo + path | Git blob SHA-1 | Observation category |
|---|---|---|
| GZDoom `CMakeLists.txt` | `8a1becdb8546036d117f63db0a18c5a45541a8ba` | CMake 3.16, C++17, conditional vcpkg/Windows options |
| GZDoom `vcpkg.json` | `69ba288e4957eb76c6e4044953f0dd5a85d2bddc` | conditional features exist |
| UZDoom `CMakeLists.txt` | `39dcbefed262eab124f23da8efdb7b3ce331dcd9` | C++20, Python3 build tool, optional updater/LTO, nonfree flag |
| UZDoom `CONTRIBUTING.md` | `84621215c99b1da9af913d082e65e20b6d725175` | source contribution policy, not code license waiver |
| BiasedDoom `CMakeLists.txt` | `ac506cbca31c2702af87011e1b7fd83e1839813c` | C++17, conditional fastgltf, Python/glTF flags |
| BiasedDoom `vcpkg.json` | `f298e19602268bb5abb8e8e72c8a0f7d84e48ca4` | package feature dependencies and provenance questions |

**Negative location check:** UZDoom root `vcpkg.json` path lookup returned NOT_FOUND at pinned SHA; this is a path-specific observation, *not* proof that all vcpkg/other manifests or dependencies are absent. No complete transitive SBOM prepared.

Previous plans: `SNE-000D-REPRO-BUILD-COMMANDS.md`, `SNE-000F-BUILD-ENTRY-GATE.md`, F-01/F-02 permissions and F-00 source claim catalog. This ledger is an author synthesis, not independent G1/G7 or an executed G4.
