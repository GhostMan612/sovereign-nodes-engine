# SNE-WO-F03 — Native Windows build readiness and reproducibility blueprint

- Phase: `SNE-P00`; sub-workstream **F-03**; documentation version **v1.2.0**.
- Required clean SNE preimage/parent: `f2f2cfec676b9a5254fa2a5a7e6f08198581fa09` (operator published F-02).
- Game source pin: `44034e97fd22129f919a18cadceb84466ef1bcd3`. This is source-only, not an original built PK3.
- Candidate pins: GZDoom `c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7`; UZDoom `dbedcc894fb6866c48520cf27ae773f9957024b9`; BiasedDoom `6147e0670458e48e63d1a40750f36dfc68b00f7f`.
- **STATE: DOCUMENTATION-ONLY / AUTH-H NOT GRANTED / AUTH-B NOT GRANTED / BUILDS NOT RUN / INDEPENDENT REVIEW PENDING.**

## Objective

Write an agent-neutral, traceable, Windows-x64 build-admission program that can be handed to an authorized operator *after* a real read-only machine inventory, dependency/rights inspection and a discrete signed `AUTH-B` permit. Propose GZDoom as the first **control build**, UZDoom as a separately authorized comparator, BiasedDoom as a quarantined experimental technology probe. None is a selected foundation.

## Deliverables

1. Exact host inventory and version questions for Dell Latitude 5400 reference profile; none reported as measured.
2. Candidate source and dependency identity ledgers, CMake option assertions, generator/CRT and no-auto-network defaults.
3. Provisional, explicitly *NOT EXECUTED* Windows/MSVC command patterns; separate configure/compile/resource/evidence phases.
4. Build failure classification and reproducibility admission: two fresh isolated attempts with matched effective inputs, binary/resource hash accounting, meaningful non-determinism triage.
5. Per-candidate blank JSON records for host, dependencies, build attempt, resources and reproducibility adjudication.
6. Rights/security/reviewer/stop conditions, complete overwrite manifest, SHA-256 file ledger and PowerShell exact staging instructions.

## Operator authorization and dependency graph

- Read-only host metadata requires specifically signed `AUTH-H`. An unsigned template or this ZIP cannot provide it.
- Actual engine source checkout, CMake configure and compilation require a separate scoped `AUTH-B`, with exact candidate, source SHA, output paths, dependency permissions and expiration. This work order **does not request approval to execute by default**.
- `AUTH-B` is **not** `AUTH-T` (game launch), `AUTH-P` (GPU trace), `AUTH-I` (implementation), or `AUTH-D` (distribution).
- Independent F-00 source-review signoff and F-02 original PK3/IWAD identity are still missing from the presented record; no gate is promoted because this text exists.

## Final documentary acceptance (not technical G4)

The authored documents are internally consistent, source pins and commit preimages checked, paths and failure oracles explicit, JSON/ZIP verified, and all measurements/authorizations remain null/NOT RUN. Operator separately stages and publishes the file-exact overlay. **P00-G4 remains NOT RUN.**

## Exclusions

No game/source code patch, build, SDK installation, `git clone`, `git pull`, WAD extraction, GPU load, Python interpreter embedding, network access, upstream PR, commercial asset packaging, private genealogy, Mantle vault access, local user machine action or remote Git mutation. Revisit only under a separate signed execution work order.
