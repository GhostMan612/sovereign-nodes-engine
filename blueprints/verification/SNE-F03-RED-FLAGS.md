# F-03 — Build output false positives and high-risk diagnostics

| Misleading signal | Why it is insufficient | Required additional proof |
|---|---|---|
| CMake prints "Configuring done" | some option/dependency assumptions unresolved | inspect effective cache, exit code and configure warnings |
| Target EXE exists | it may be stale from another build | clean tree + target generation/mtime + SHA manifest |
| A build reaches 100% | missing resource package or sidecar | runtime-package completeness and dependency inventory |
| Engine opens a game menu | not actual Sovereign Nodes gameplay | separate AUTH-T and original GapNode proof |
| Python installed under WSL | Windows CMake may not find native Python | inspect approved native interpreter path, versions and tools |
| vcpkg.json exists | dependencies may float or lack license clearance | resolved lock/ports/feature baseline and notices |
| UZDoom `USE_UPDATER=OFF` | says nothing about resource/other downloads | review all actual configure-time dependency fetches |
| BiasedDoom Python flag omitted | source default may enable embedding | explicitly set OFF, verify cache/linked targets |
| BiasedDoom glTF appears in README | option may require fastgltf and build distinct binary | actual CMake cache, compile output and later runtime |
| Two EXEs differ | timestamps/debug paths can be nondeterministic | compare inputs, binary diff and reproducibility traces |
| Different ABI/runtime libraries ignored | may only fail when deployed | record CRT/static imports, SDK and resource sidecars |
| Bit-identical EXEs | no game parity, rights, frame times or full G4 independent signoff | G3/G2/G5/G7 distinct proofs |
