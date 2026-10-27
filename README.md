# SCGraph2 2.2.29

Open `index.html` locally, or deploy the archive contents with GitHub Pages. No build or external dependencies are required. This release continues the existing SCGraph2 codebase.

## Concise results by default

Quantitative analyses now open with a short Comparison heading, the observed result, and a practical interpretation or statistical Alert. Select **Show detailed results** in Results for the complete existing calculations, shading definitions, and session-by-session explanations. Switching formats updates the text immediately without recomputing statistics or replotting the graph. Both formats are retained in saved analysis records, and the display choice persists in session JSON. Reset restores concise results. Insert Analysis Results uses the selected format and includes any sample-size caution.

- PND reports the qualifying count, percentage, baseline maximum/minimum, and requested practical distinction category.
- Mann–Whitney reports directional pairwise non-overlap (NAP), the approximate one-sided p-value, the descriptive category, and the alpha decision.
- Trend + 0.3 IQR reports the count crossing the improvement-side criterion and the one-sided binomial result.
- Tau-U separates the raw and baseline-corrected effects. The raw percentage describes net pairwise non-overlap, not a percentage of individual observations. A corrected p-value remains unavailable; the uncorrected p-value is never presented as a test of corrected Tau-U. One-sided remains the default, with the existing two-sided option retained and explicitly labeled.

A nonsignificant test says that clear statistical evidence of change was not found; it does not claim equivalence or prove no change. PND and the requested practical distinction categories remain descriptive, separate from p-values.

## Small-sample caution

Whenever an analyzed phase has fewer than five observed data points, a labeled caution identifies that phase and its count and asks the reader to interpret statistical results with caution. It appears in both result formats and inserted reports. Blank sessions and ghosted points retain their graph positions but do not count toward five observations. Exactly five observations do not trigger the caution. Unselected phases do not affect it.

Older saved sessions default to concise results. Rerun their analyses to generate the new summaries, or select Show detailed results to read their preserved output. Where the original series and phase titles match the restored data, the caution is also available for older saved results.

## Retained behavior

Statistical formulas, directional shading, Tau-U phase-length choices and trend/residual-IQR reference, PND criterion shading, the level-only Mann–Whitney reference, session-gap parsing, and fresh replots for every quantitative analysis are unchanged. The standalone HTML remains self-contained. Session JSON schema version is now 52.

## Validation

95 targeted JavaScript/app-DOM checks passed. They cover concise and detailed views, default-data figures, PND category boundaries, one- and two-sided language, increase/decrease directions, corrected Tau-U limitations, the exact caution threshold, missing/ghosted points, nonadjacent selected phases, report insertion, reset, JSON roundtrips, legacy sessions, safe text rendering, and live switching without a graph redraw. Seventeen statistical, parsing, and shading functions were verified unchanged from 2.2.28. JavaScript syntax and ZIP integrity/content matching were checked. No full-browser interaction review was performed.
