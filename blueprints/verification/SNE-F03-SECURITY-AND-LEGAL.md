# F-03 — Security and licensing limits for build preparation

- This ZIP contains only text/JSON specifications. No third-party engine source, proprietary IWAD, binary, dependency archive, driver or Python executable is distributed.
- Root source licenses and transitive libraries may have mixed conditions; record per-file notices, bundled fonts/shaders/music/branding/resource PK3 licenses before even proposing redistribution. A GPL codebase is not permission to ship commercial Doom IWADs.
- UZDoom pinned `CONTRIBUTING.md` expressly rejects AI-assisted upstream PRs; comply with upstream contribution policy independently of downstream GPL rights. Do not auto-submit any patch.
- BiasedDoom embedded CPython is native execution and not a sandbox. Keep `BIASEDDOOM_ENABLE_PYTHON=OFF` in future baseline, independently verify flags and linked packages. No live Mantle vault, real genealogy, untrusted mod or private file access.
- Network default deny. Store private build logs with user paths off-repo; publish only redacted summaries/hashes. Do not download from floating URLs, bypass antivirus, elevate, install drivers or auto-consent to licenses.
- Legal/license work is separate F-06 `AUTH-S`; distribution is separate `AUTH-D`. Neither approval comes from `AUTH-B`, a build PASS or this package.
