# F-00 — Godot-to-ZScript handoff source review and uncertainty

## Pinned producer/consumer

- Godot writer: `https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodes/src/world/fps_launcher.gd#L190-L210`; `hasParadox` is derived via Godot `bool(...)` (source blob `7bbd446af0fb3e9c7f8e2646863101e06fc23f3a`).
- ZScript reader: `https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/zscript/sn_handoff.zs#L158-L248`; `ScanInt(text, KEY_PARADOX, paradoxFlag)` then `h.hasParadox = paradoxFlag != 0` (blob `c83a8058d602ee6d1c6a7aca2792a5d408db2ebb`).
- `ScanInt` calls `ScanRaw` then `s.ToInt(0, out)`. The actual engine-runtime semantics of `ToInt` on `true`/`false` are **not determined by this inspection**; don't assert a known boolean result or game bug.
- Schema missing/newer codepath **warns and continues** rather than enforcing a fail-closed schema. Observed parser uses string searches, not a demonstrated robust bounded JSON parser.

## Mandatory independent read-only checks

1. Trace producer JSON serialization to concrete text form and verify no custom conversion to `1/0` before consumption.
2. Inspect `ToInt` method implementation at the exact candidate source revision; distinguish parse-success bool, default initialized value and integer output. If not found, record `UNVERIFIED`.
3. Trace `ScanRaw` substring match and quoted-string parsing; identify duplicate-field and escaped-quote risks separately from whether those are exploitable.
4. Verify how the consumer chooses the TEMP file, missing file behavior, runtime schema warning and caller fallbacks without leaking real Mantle data.
5. Identify what would be learned from synthetic `true`, `false`, numeric `1`, numeric `0`, absent, stale, malformed and future-schema cases.

## Review disposition

Source shape mismatch is **supported**, runtime outcome is **NOT RUN**. The proposed future strict JSON-boolean parser/nonce/schema v2 contract is design-only; it has not been implemented. Any change to game source requires a separately approved F-02 repair work order, not this audit.
