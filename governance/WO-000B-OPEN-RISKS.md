# WO-000B — Open engineering risks

| ID | Category | Probability (qualitative) | Impact | Handling |
|---|---|---|---|---|
| SNE-R-B01 | ZScript compatibility breaks | Unknown | Critical | A01/A02/A06 and log traces |
| SNE-R-B02 | GPU overload with shadowed lights / models | High plausibility, unmeasured | High | Low profile L, UHD 620 benchmarks |
| SNE-R-B03 | Conditional glTF loader disconnected at build | Unknown | High | Macro, target, registration and runtime proof |
| SNE-R-B04 | Python mods gain unwanted file/network access | Unknown, capability risk | Critical | Off by default, separate trust analysis |
| SNE-R-B05 | Licensing of bundled third-party assets | Unknown | High | Complete bill of materials + notice review |
| SNE-R-B06 | Downstream divergence from GZDoom/UZDoom | Likely if broad patches | High | Minimal commits, upstream tracking, explicit diff discipline |
| SNE-R-B07 | Real genealogy data enters game test environment | Preventable | Critical | Synthetic-only, no private dump or real names |
| SNE-R-B08 | Toolchain mismatch C++17 vs C++20 | Likely environment-specific | Medium | toolchain-pinned Windows baseline |
| SNE-R-B09 | Source evidence mistaken for runtime PASS | Process risk | Critical | Gate record explicitly separate source/build/runtime/acceptance |
