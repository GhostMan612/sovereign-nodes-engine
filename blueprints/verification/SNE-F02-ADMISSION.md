# F-02 admission and preflight checklist (NO APPROVAL)

**All entries currently unchecked.** Actual host/file access must be separately approved and performed on the operator device; these written criteria are not execution instructions.

- [ ] Confirm F-01 `725fded39c0d50139ab76182211e32375bc2764e` published, F-00 independent P0 review still open or qualified reviewer evidence provided.
- [ ] Confirm actual operator signature for exact `AUTH-R` or `AUTH-H` task, allowed source/host, expiry, revocation and private scope digest. Unsigned template is `BLOCKED`.
- [ ] Confirm source and output paths are canonical; no broad `C:\`, wildcard reads of user profiles, symlink/junction traversal or original-game writes.
- [ ] Confirm metadata collection reads no serial number, credentials, WAD bytes or real Mantle data into public records.
- [ ] Confirm lawfully held IWAD/PK3 existence *privately* and exact hashes when permitted; missing legal provenance ⇒ `BLOCKED` for gameplay.
- [ ] Confirm B0/source SHA and signed change manifest before `AUTH-F`; B1/B2 output root outside SNE and authoritative game checkout.
- [ ] Confirm `AUTH-T` separately for every engine or game launch, original game proof and negative control definitions.
- [ ] Pre-register expected output, stop conditions, max duration, retention, abort/rollback and reviewer; fail closed on any mismatch.

Results at release: `AUTH-R/H/F/T = NOT APPROVED`; OS/PK3/validation/cases `NOT RUN`. Review results cannot be inferred from a ZIP extraction.
