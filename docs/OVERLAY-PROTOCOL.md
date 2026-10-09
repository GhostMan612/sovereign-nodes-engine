# Downloadable overlay protocol

Future ZIPs preserve the top-level `sovereign-nodes-engine/` prefix so they can be extracted into `C:\`. Each overlay must ship a manifest identifying files to add/replace, baseline expectations, conflicts, and a post-extraction review checklist. Overlay authors may serve as both architect and reviewer, but acceptance remains a distinct gate requiring independent verification and operator approval. Prefer minimal additive overlays; never wipe or recreate the whole repository to apply an update.
