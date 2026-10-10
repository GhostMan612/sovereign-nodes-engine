# F-00 — Sprite/GLDEFS source controversy and falsification plan

## Source facts (NOT rendered results)

- Source game `zscript/core.zs` at `44034e97fd22129f919a18cadceb84466ef1bcd3`, blob `61fb41c797d909404153d77bab894704637ceba4`, lines 63–74 declares sprite families `ORESHA`, `TOOLA`, `ELEC` and frames `ORESHAA0`, `TOOLAA0`, `ELECA0`.
- Source game `game/GLDEFS.txt`, blob `b98abc8de454617fc5681fb585ac8d41cee71bc9`, lines 21–59 declares three pointlights and light-to-texture names including `ORESHAA0` and `TOOLAA0`.
- GZDoom `src/r_data/sprites.cpp` at `c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7`, blob `0a7be96a12003a4996b0ea1ca2b275eec6840785`, lines 297–333 explicitly describes **four-character sprite family + frame letter + rotation** and builds a four-character name hash. This makes >4-character family conventions **suspicious** but doesn't by itself prove all textures fail to load or GLDEFS rejects the names.

## Reviewer questions

1. Which game resource archive entries and sprite namespace conventions would GZDoom/UZDoom actually recognize? Distinguish filename, texture name, actor `Sprite` field and GLDEFS `texture` lookup.
2. Does the game packager normalize or alias long names (check code and fixture generator), or is its existence check independent of engine parser semantics?
3. Are `ORESHAA0` and `TOOLAA0` syntactically legal actor sprite identifiers at this engine revision, or could parser truncation/mapping cause another error? Examine full relevant call paths, not a comment alone.
4. Does `ELECA0` provide an unambiguous known-good control? Check loaded archive and collision/interaction separately from visible texture.
5. Is a proposed fix one-variable, disposable and independently hash-differentiated from the original PK3?

## Counterclaim acceptance

If independent primary-source tracing shows compatibility aliases or special actor texture handling, **revise the hypothesis**; do not preserve the defect merely because it was anticipated in WO-C. If the path still depends on runtime, label it `INFERENCE / NOT RUN` and route to F-02 with a fresh authorization request. **G3 does not PASS from source reading.**

Related: `blueprints/verification/SNE-000F-SPRITE-TESTS.md`, `SNE-F00-CLAIM-CATALOG.md`.
