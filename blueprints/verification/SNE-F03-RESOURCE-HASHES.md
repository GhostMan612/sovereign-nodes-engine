# F-03 — Executable, resources and binary-sidecar integrity

## Future capture contract

Per approved build attempt, fingerprint raw SHA-256, byte size, known role and build-tree-relative name for each executable, engine resource PK3, DLL, translation, shader/resource bundle, required config and relevant packaging manifest. Separate items built internally from external dependencies/official assets; source commit alone is not output identity.

Do not assume one filename, output path or EXE is universal for all forks. Determine actual configured target(s) and copy nothing into SNE docs without rights check. Private evidence may include a structured binary manifest with file hashes and build command; public summary includes only licensed/sanitized values. Proprietary IWAD files never enter build artifacts.

A successful engine EXE hash does not prove custom `MAP01`, GLDEFS, sprites, handoff or lawful resource integration. F-04 must reference this exact fingerprint before testing. Sign-off for any redistribution remains separately blocked by G2 and `AUTH-D`.
