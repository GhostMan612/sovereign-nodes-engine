# F-02B — Disposable B0/B1/B2 fixture isolation, byte-diff and safe cleanup

## Partition

| Baseline | Bytes | Intended permitted workspace | Promotion rule |
|---|---|---|---|
| B0 | immutable actual game PK3 and input source SHA at `44034e97fd22129f919a18cadceb84466ef1bcd3` | original authoritative repo READ-ONLY; approved external copy for examination | C-series **unchanged game** only if hash matches original |
| B1 | one-variable copied sprite/GLDEFS fixture | operator-selected external disposable root, only after AUTH-F | a fixture result, never B0 pass |
| B2 | synthetic JSON true/false, number, invalid/stale controls | distinct external disposable root, only after AUTH-F | a fixture result, never native Godot parity alone |

## Preparation invariants

- Approve exact canonical read roots, permitted output file list/byte limit and symlink/junction restrictions. No copies into `C:\sovereign-nodes-engine` or authoritative game repo.
- Before each mutation, record original raw SHA, copy raw SHA, file count and member manifest. Changing one variable must be checkable at the archive member or JSON-field level—not just a verbal claim.
- For every fixture, record `fixture_id`, `parent_sha256`, `output_sha256`, `modified_entries`, `diff_digest`, `expected_oracle`, `negative_control`, `new_run_id`, `expiry`, `raw_evidence_private_ref`.
- Rebuild PK3 only under approved `AUTH-F` if scope explicitly names interpreter/tool and output path. Building fixture does not grant engine/game launch authority.
- Cleanup only operator-listed disposable bytes under approved path; stop if identity/path mismatch or unexpected files appear, preserve original and evidence.

All B0/B1/B2 checksums and workspace locations are **UNKNOWN** at package release. Use `templates/SNE-F02-FIXTURE-CONTROL.json` as an unexecuted form.
