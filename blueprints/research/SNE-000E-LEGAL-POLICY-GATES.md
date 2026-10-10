# WO-E — Legal, contribution and artifact provenance gates

## Different legal questions

- **Code license:** GZDoom and derivatives contain GPL and file-specific historical notices; downstream code modifications require preserving obligations according to actual files and distribution choices.
- **Bundled assets:** branding, textures, audio, resource PK3s and model libraries need separate rights audit; an engine code LICENSE is not a commercial IWAD license.
- **Upstream contribution policy:** inspected UZDoom `CONTRIBUTING.md` rejects AI-generated or AI-assisted submissions. This is a policy of that upstream project and does not replace its GPL terms. Do not send generated patches upstream.
- **Downstream maintenance:** a compatible license may allow a responsibly maintained independent fork subject to full requirements; do not automatically equate with permission to use its logos/brands.
- **BiasedDoom embedded Python:** native-equivalent process access, not sandboxed mod execution; require explicit operator trust and disabled baseline.

## Minimum release review checklist

1. Source URL/SHA, per-file copyright/notice, SPDX/actual legal text and transitive library origin.
2. Exact included compiled executables, runtime DLLs, static dependencies, resource PK3s, fonts/shaders, launch/update helper and all assets.
3. Whether the repository/assets are independently authored, GPL-compatible or restricted; private/copyrighted IWADs must never enter public artifact.
4. GPL source access, change notices, license text and attribution obligations planned before distribution.
5. Trademark/branding/name and logos evaluated separately.
6. Independent qualified rights review and operator signoff recorded; unknown item blocks distribution.

The package is not legal advice or clearance; no engine binary/source is distributed here.
