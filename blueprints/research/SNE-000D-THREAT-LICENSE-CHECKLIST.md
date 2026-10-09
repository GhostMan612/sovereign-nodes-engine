# WO-000D — Build/benchmark security and rights checklist

- [ ] No commercial IWAD or mod assets committed, packed into SNE ZIP, or shared in logs; path/hash only when lawful and redacted.
- [ ] All test data synthetic; no Mantle event ledger, real person graph, private cards, passwords, API tokens or user home directory captured in a public trace.
- [ ] Builds (when authorized) use immutable checkout and isolated write paths. No unreviewed install helpers, auto-update, Defender changes or global toolchain modifications.
- [ ] No untrusted Python in BiasedDoom; embedded CPython is not sandboxed, and runtime opt-in may authorize every loaded manifest. Default baseline explicitly disables it at compile/request level subject to verified behavior.
- [ ] Source/build URL, SHA-256 and package signatures checked before dependency download; no `curl | sh` execution.
- [ ] Dependencies and bundled engines include original notices, GPL source access plan, and independent asset/branding review.
- [ ] UZDoom upstream PR no-AI policy respected. Independent licensed downstream fork obligations are evaluated separately.
- [ ] Benchmark logs scrub usernames, hostnames, process dumps, absolute home paths and gameplay private data; raw traces stay outside public Git.
- [ ] Test-only Windows permissions, process isolation and firewall impact reviewed before connecting any multiplayer/server engine.
- [ ] The system under test does not write to authoritative Mantle vault or graph. No external data connector activated by tests.

**Failure policy:** any unknown rights or privileged execution concern blocks promotion to an authorized execution/run, even if a demo visually succeeds.
