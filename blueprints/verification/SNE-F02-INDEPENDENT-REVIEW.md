# F-02 — Reviewer challenge and signed disposition requirements

Distinct from the research/overlay author, an independent source reviewer must evaluate critical claims before G1/G7. A future game tester and independent test reviewer separately certify *actual* B0/fixture runs. Neither role exists as an accepted signed record in the current package.

## Challenges reviewer must address

- Confirm pinned packager intentionally omits SNDINFO and that omission is not mislabeled a PK3 error.
- Independently examine `validate_pk3.py` missing-path observation and actual checks implemented by `build_pk3.py` / `validate_wads.py`.
- Trace ZScript `ScanInt`/`ToInt` and bool producer without claiming observed true/false from code alone.
- Examine raw frame names, four-character sprite loader and GLDEFS texture binding as *separate* lookup questions; attempt to falsify the assumed mismatch.
- Confirm original B0 and each B1/B2 mutation are byte-identifiable and original project untouched; negative controls detect IWAD fallback.
- Review legality/privacy of resource inventory and host metadata without authorizing extraction of original IWAD bytes.

## Output

Use `templates/SNE-F00-INDEPENDENT-REVIEW.json` for actual F-00 source claims; use `templates/SNE-F02-CASE-RESULT.json` for separately authorized F-02 static/runtime evidence when applicable. Record counterevidence, disagreements, affected G1/G3/G6, and operator disposition; missing independent source review remains PENDING.

No F-02 template is pre-signed or independently verified.
