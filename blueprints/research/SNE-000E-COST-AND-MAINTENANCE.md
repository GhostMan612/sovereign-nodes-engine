# WO-E — Maintenance economics without fabricated estimates

## Variables to measure in an approved controlled trial

| Variable | Method | Current value |
|---|---|---|
| Checkout/build preparation time | fixed environment capture and setup diary | UNKNOWN |
| Clean build elapsed time | measured configure + resource + link, same host | NOT RUN |
| Update merge conflict count | one strictly pinned upstream patch trial | NOT RUN |
| Local patch count/churn | change manifest, LOC/file/module ownership | NO FORK EXISTS |
| Actor/script compatibility repair time | owner-approved isolated fixture validation | NOT RUN |
| Renderer change regression surface | log render backends, resource caches, shaders, fonts, UI, save | NOT ASSESSED |
| GPL/source release support burden | component/asset transitive license review | UNASSESSED |
| Windows binary signing/release burden | release threat and installer policy review | NOT PLANNED |
| Low-end GPU downgrade costs | compare P0-P3 frame traces and visual features | NOT MEASURED |

## Decision rule

Do not assign monetary amounts, engineer-week figures or maintenance percentages based on source tree size. Rank testability and regression exposure qualitatively now; score burden only after a bounded reproducible update exercise. Keep separate: baseline engine upkeep, downstream custom features, bundling/licensing, and game compatibility fixes. This avoids hiding a custom renderer fork's long-term cost behind the short initial model-loading demo.

## Freeze strategy

Once a candidate eventually passes, pin exact upstream release and dependency lock. Track security updates and compatibility explicitly. Preserve a downgrade path to stock-like P0 gameplay and avoid editing private Mantle systems from fork work.
