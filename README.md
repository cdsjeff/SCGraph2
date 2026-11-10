# SCGraph2 v79

SCGraph2 is a standalone app for graphing and analyzing single-case data. Open `SCGraph2.html` in a browser to use it offline. To publish with GitHub Pages, unzip the files at the root of the publishing branch and select that branch and its root folder in Pages settings. `index.html` and `SCGraph2.html` are identical.

## Hide p-values

In Analysis, check **Hide p-values** below the phase selector. Both Results formats, new report inserts, and graph exports omit p-values and significance conclusions while keeping effect sizes, descriptive results, and overlays. Uncheck to restore the full results without rerunning the analysis.

The setting is saved with your project. Projects saved before this setting was added default to showing p-values. Material already inserted into a report stays as written.

Validated with DOM integration and SVG/PNG raster checks covering simple and detailed results, live toggling, older and new project states, exports, and new report inserts.

## Earlier release v78

# SCGraph2 v78

Open `index.html` or `SCGraph2.html` in a modern browser. For GitHub Pages, extract the ZIP into the repository root and select that branch/root in Pages settings. The app works offline.

## PND / NAP

In **Analysis → Level**, open the settings arrow next to **PND / NAP** and choose the **Non-overlap measure**. Select **NAP — all pairs** to compare every active baseline score with every active intervention score in the chosen improvement direction. The result shows the percentage and the favorable, tied, and unfavorable pair counts. Each tie receives half credit. NAP has no single cutoff or shading. Use **Mann–Whitney** for the exact one-sided p-value for the same pairwise comparison.

Classic **PND — best baseline score** is the default. It keeps its extreme baseline cutoff and shading. Changing the measure updates an active comparison, and the project remembers the selection. Older projects without the setting use classic PND. `NAP, 1, 2` selects and runs NAP; `PND, 1, 2` runs the selected measure.

The built-in data give PND 50% and NAP 87.5% (13 favorable, 2 ties, 1 unfavorable out of 16 pairs).

Checked method switching, both improvement directions, all ties, nonadjacent phases, missing and ghosted positions, commands, new and older saved projects, report inserts and graph snapshots, SVG and raster output. The exact Mann–Whitney and Tau-U results, CDC and IQR agree with v77. JavaScript syntax and ZIP integrity checked.

## Earlier release v77

# SCGraph2 v77

Open `index.html` or `SCGraph2.html` in a modern browser. For GitHub Pages, extract the ZIP into the repository root and select that branch/root in Pages settings. The app works offline.

## Exact rank tests

- **Uncorrected Tau-U** and **Mann–Whitney** share the exact conditional distribution of the between-phase sign count `S_AB`, equivalent to `U = (nA × nB + S_AB)/2`. The test counts assignments of pooled observations to phases of the observed sizes, retaining ties.
- **Baseline-corrected Tau-U** uses the exact distribution of adjusted Kendall `S = S_AB − S_A`. The calculation counts chronological orders within Phase A; the order of Phase B does not enter the statistic.
- The one-sided test counts scores at least as large as observed in the selected improvement direction. Tau-U's two-sided option counts scores at least as large in absolute value. Counts are computed with integers; displayed p-values are rounded.

On the built-in data, one-sided exact **Mann–Whitney p = .0714** and **corrected Kendall S p = .0833**. The corrected S is 11, and the uncorrected and corrected Tau effects are .75 and .6875. The signed effects, graphs and CDC calculations are unchanged. Results, report inserts and exported Results panes identify the exact method. Rerun an older saved analysis to refresh its p-value.

These conditional permutation tests assume that scores are exchangeable across sessions under the null. They do not adjust for serial dependence or for selecting the contrast in Auto mode. If a comparison exceeds the app's exact calculation limit, it reports the p-value as unavailable and still shows the effect size and graph.

## Validation

Checked against independent exhaustive enumeration on 81 small datasets, including ties, unequal phase sizes, both directions and both tails. Verified an additional 30+30 tied comparison, large count arithmetic, the explicit limit, results, unchanged effects and plots, project save/load, report inserts and snapshots, SVG and PNG raster output. This was DOM and raster validation; no full-browser layout run was performed. JavaScript syntax, ZIP integrity and matching HTML copies checked.

## Earlier release v76

# SCGraph2 v76

Open `index.html` or `SCGraph2.html` in a modern browser. For GitHub Pages, extract the ZIP into the repository root and select that branch/root in Pages settings. The app works offline.

CDC-NonPar Trend now reports the fitted Phase A Theil–Sen slope in score units per session in simple and detailed Results. The built-in data show +0.5 score units per session. The reported slope is the rate used to project the baseline reference; it does not alter the cutoff, crossing counts, binomial p-value or plots. It is included in inserted analysis results and exported Results panes. Rerun CDC Trend to add the slope to a result saved in an older version.

Checked rising, flat and falling trends, a nondefault reference phase, both Results formats, reports, SVG and project save/load. CDC Level results and CDC Trend computations and overlays agree with v75. JavaScript syntax, ZIP integrity and byte-identical HTML copies checked.

## Earlier release v75

# SCGraph2 v75

Open `index.html` or `SCGraph2.html` in a modern browser. For GitHub Pages, extract the ZIP into the repository root and select that branch/root in Pages settings. The app works offline.

The default CDC-NonPar multiplier is now **0.20 × IQR** for both Level and Trend. New and reset projects, and older projects without a saved multiplier, use 0.20. Explicit saved values, including 0.30 and zero, still load as entered. PND continues to use the Phase A maximum or minimum. The built-in data still give four of four CDC Level crossings, with one-sided p = .0625.

Checked startup and reset, both CDC modes, a dataset where the new cutoff changes the crossing count, saved and missing multipliers, and unchanged PND, Tau-U, Mann–Whitney and trend IQR results. JavaScript syntax and ZIP integrity checked.

## Earlier release v74

# SCGraph2 v74

Open `index.html` or `SCGraph2.html` in a modern browser. For GitHub Pages, extract the ZIP into the repository root and select that branch/root in Pages settings. The app works offline without a build or external dependencies.

## Shared p-value for the level comparisons

**Level → Tau-U uncorrected** and **Level → Mann–Whitney** share the Mann–Whitney normal approximation with tie and continuity corrections. Their one-sided p-values agree for the same observations and improvement direction. Tau-U continues to display the signed Tau effect size and use it for the cloud. Its optional two-sided setting uses the corresponding two-sided Mann–Whitney approximation for the raw phase contrast.

On the built-in Sniffing data (`2,4,5,2|6,7,4,5`), the two Level comparisons display one-sided **pEst ≈ .053**. Uncorrected Tau remains .750. The baseline-corrected effect and its separate p-value calculation are unchanged: the built-in data give corrected Tau-U .6875 and one-sided **pEst ≈ .068**. In the corrected Results, the uncorrected line is labeled as the Mann–Whitney estimate.

Previously saved results and report snapshots remain as captured. Rerun Tau-U to refresh an older result. This release is separate from v73.

## Validation

Checked the actual Level and Trend buttons and displayed results in JSDOM. Confirmed that the one-sided Mann–Whitney routine agrees with v73, raw Tau-U agrees with that routine, and the optional two-sided result is symmetric. Tested ties, all-tied data, small phases, both directions, missing and ghosted sessions, and preservation of baseline-corrected estimates, effect sizes and overlays. Verified save/load, older-state reruns, IQR outlier legend and results, report insertion and graph snapshots. The exported SVG Results pane was rasterized to PNG with Sharp and visually inspected. JavaScript syntax, ZIP integrity and byte-identical HTML copies were checked. This is DOM and raster validation; no full-browser layout run was performed.

## Earlier release v73


# SCGraph2 v73

Open `index.html` or `SCGraph2.html` in a modern browser. For GitHub Pages, extract the ZIP into the repository root and select that branch/root in Pages settings. The standalone app runs offline without a build or external dependencies.

## IQR legend and outlier results

Run **Level → IQR** or **Trend → IQR**. The Legend shows the series' observation symbol with a red center, labeled **Outlier**. Click the shared Legend / Results pane, or focus it and press Enter or Space, to see the results.

- Results state the number of flagged observations and list each one's session, phase and value, plus the reference phase whose outer fence it crossed. A point crossing several visible references appears once, with each reference identified.
- Detailed results also give the applicable Y limits at that session and identify level or trend-residual fences. Original fractional entries are retained. When displayed session numbering differs, the row includes both the underlying session and its displayed label.
- If no observations cross the visible fences, Results say so. Hiding Phase 2's IQR updates the list to match the remaining red dots; Phase 1's projected reference remains in effect. If all the selected references are hidden, the result explains that instead.
- The list is included on the exported Results face and in **Report → Insert → Analysis Results**. New graph snapshots retain the selected Legend / Results face. Existing snapshots stay static.

The existing outer-fence definition is unchanged: **Q1 − 3×IQR** and **Q3 + 3×IQR**, with the app's existing interpolated quartiles. Level uses scores; trend uses residuals about the fitted line. Phase 1's reference projects into later phases, and other references stay local. Missing and ghosted observations do not receive dots. These are descriptive flags, not individual-point significance tests, and no observation is removed or statistical calculation changed.

Current project saves retain exact reference phase indices, including repeated phase names. Older projects recover their reference from saved context when unambiguous. If a reference cannot be identified safely, the result asks for the IQR analysis to be rerun.

Reference: NIST/SEMATECH e-Handbook of Statistical Methods, *What are outliers in the data?* https://www.itl.nist.gov/div898/handbook/prc/section1/prc16.htm

## Validation

187 checks passed in JSDOM, covering the accessible symbol, simple/detailed lists, strict fence boundaries, no-outlier and hidden-reference cases, trend residuals, fractions, missing/ghosted sessions, live edits, reference visibility, deduplication, repeated phase labels, legacy/current project saves, displayed numbering and calendar identity, multiple graphs/tiers, report insertions/snapshots and complete long lists. Base results and numerical overlays matched freshly retrieved v72 across ordinary, missing/ghosted and decrease datasets. Numerical functions, outer-fence classification, red-dot drawing, goal colors/styles and Tau-U cloud functions were verified unchanged.

Ten SVGs, including full/compact and all/selected graph exports, were rasterized to PNG with Sharp. Representative level, trend, mixed-graph/tier and long-list figures were visually inspected. JavaScript syntax, ZIP integrity and byte-identical root/standalone HTML files were checked. This is DOM and raster validation; no full-browser layout run was performed.

Build/help metadata identify v73. The SCGraph2 framework and unrelated menus, exclusive panels/categories, report tools/carets, three independently styled/colored goals, analyses, cloud darkness/plain classroom points, grids, fractions/ratings, session mapping and export choices are preserved. This release is saved separately from earlier versions.

## Earlier release v72


# SCGraph2 v72

Open `index.html` or `SCGraph2.html` in a modern browser. For GitHub Pages, extract this ZIP into the repository root and select that branch/root in Pages settings. The standalone app runs offline without a build or external dependencies.

## Finding and editing goal lines

Use **Graph → Goal Lines** in the top menu. This opens the exclusive Graph Controls panel, opens its Graph category, scrolls directly to the visible **Goal Lines** heading and focuses the goal selector. The controls remain available at **Graph Controls → Graph → Goal Lines**.

- **New goal line** clears the goal editor for another line and focuses the Y value. Pick its series/tier, phase range, color and line type; entering a complete Y value creates it automatically.
- Add up to **three independent goals per series/tier**, including different values over the same phase range. All added lines remain visible together. The selector chooses which one you are editing.
- Each listed goal now has **Edit** and **Remove** buttons. Edit loads that line's value, phases, style and color. The list shows a color sample/name and line type.
- **Goal line color** provides the same eight discrete colors as the data line/symbol palette: Black, Blue, Red, Orange, Green, Purple, Teal and Gray. Each goal and its on-graph label use that goal's chosen color. Changing a goal does not recolor observations or other goals.
- Style choices remain Standard, Thick, Double, Dotted and Dashed (goal line). All five remain in the phase boundary selector. Color changes apply to goals; phase boundaries retain their existing color.

Values, styles and colors update automatically. Color edits commit a valid pending Y value before redrawing. A color choice alone does not create an empty goal. Project save/load, editable graph JSON, SVG/PNG exports and new report snapshots retain independent goal colors. Existing snapshots remain static.

Older goals without a saved color retain the original series-based goal appearance. Valid imported custom colors are retained; invalid colors fall back safely. The three-goal limit, legacy projects with more than three goals, removal/cancellation behavior and original single-span typed goal commands are preserved. Typed commands that update an existing goal retain its color.

## Validation

164 checks passed in JSDOM, covering menu navigation/focus and exclusive panels, the visible heading, eight accessible color buttons, Edit/New controls, independent line and label colors, live updates, pending Y changes, project and graph JSON, legacy/custom/invalid colors, command behavior, the three-goal cap, tooltips, and unchanged descriptive/statistical results. The IQR outer-fence functions, numerical functions, Tau-U cloud and shared line-style rendering were verified unchanged from freshly retrieved v71.

Eight all/selected and full/compact SVG exports, including calendar graphs and stacked tiers, were independently rasterized with Sharp. Pixel checks confirmed the actual selected goal colors in PNG output, including antialiasing. Representative color and combined IQR figures were visually inspected. Report snapshots retained colors and remained static. JavaScript syntax, ZIP integrity and byte-identical root/standalone HTML files were checked. No full-browser layout run was performed.

Build/help metadata identify v72. The SCGraph2 framework and unrelated menus, report tools, carets, exclusive categories, one-sided analyses, cloud settings/plain classroom points, IQR red dots, grids, fractions/ratings, session mapping and export choices are preserved. This release is saved separately from earlier versions.

## Earlier release v71

# SCGraph2 v71

Open `index.html` or `SCGraph2.html` in a modern browser. For GitHub Pages, extract this ZIP into the repository root and select that branch/root in Pages settings. The standalone app works offline without a build or external dependencies.

## Three independent goal lines and shared styles

Open **Graph Controls → Graph → Goal Lines**. Choose **New goal line**, select the series/tier, phase span, **Line type** and Y value. Add up to **three goal lines per series/tier**, including different Y values over the same phase span. Each line retains its own style. Choose an existing line to edit it; select New goal line to create another.

Goals and phase boundaries now share five line types: **Standard**, **Thick**, **Double**, **Dotted**, and **Dashed (goal line)**. The dashed option uses the original goal pattern, and is the default for new goals and goals loaded from earlier projects. Clicking a plotted phase boundary cycles through all five styles.

Changes apply automatically. Pending values are committed before save/export/report capture. Invalid entries preserve the last valid line and must be corrected or discarded before capture. Exact duplicate values over the same series/span are prevented. A fourth new goal is blocked with feedback; existing legacy projects with more than three goals per series are preserved, can be edited/reduced, and cannot add another to that series. Moving an existing line into a full series is blocked. Remove and Clear cancel relevant pending edits. Existing typed goal commands continue to update a uniquely matching span; use the goal selector to choose among multiple lines sharing that span.

Goal values, spans and styles survive project save/load, graph JSON, full/compact SVG and PNG exports, and new report graph snapshots. Earlier files are preserved separately.

## IQR outer-fence red dots

**IQR Level** and **IQR Trend** add a small red dot centered inside each active observation beyond a visible reference's outer fences: **Q1 − 3×IQR** and **Q3 + 3×IQR**. This uses the app's existing interpolated quartiles. Points exactly on a fence are not flagged; numerical roundoff is suppressed for fitted trends.

- Level uses observed-score quartiles. Trend uses residual quartiles about that reference's Theil–Sen trend.
- Each visible IQR reference uses its displayed session span. Phase 1's reference also assesses later observations within its projected span; later-phase references stay local. A point crossing multiple visible references is marked once.
- The dot's accessible/hover description identifies the reference and limits. Fractional values retain their original fraction in the description. Global Show tooltips controls hover text.
- Hiding the Phase 2 IQR hides dots due to that reference; flags due to Phase 1's projection can remain. Switching away from IQR or toggling it off removes its dots.
- Missing and ghosted observations do not enter the quartiles or receive dots. Calendar dates and displayed session numbering do not affect classification.
- These are descriptive reference flags, not individual-point significance tests. Observations remain in all calculations. The IQR legend explains the red dot, and exports/new report snapshots include it.

Reference: NIST/SEMATECH e-Handbook of Statistical Methods, Section 7.1.6, *What are outliers in the data?* https://www.itl.nist.gov/div898/handbook/prc/section1/prc16.htm

## Validation

186 automated checks passed in JSDOM. Checks covered independent same-span goals, the cap and safe moves, all five shared geometries and phase cycling, live updates and pending edits, legacy/current project and graph JSON, goal removal, exact/beyond outer fences, both tails, trend residuals, projected references, phase visibility, zero IQR, missing/ghosted sessions, calendar identity, fraction/tooltips and analysis toggling. Descriptive and statistical results matched freshly retrieved v70 across ordinary, missing/ghosted and decrease datasets. Numerical parsing, quartile, fitting, probability and Tau-U/cloud functions were also verified unchanged.

Fourteen all/selected and full/compact SVGs were independently rasterized with Sharp, including multiple graphs and stacked tiers. Pixel checks confirmed red observations in PNG output; level, trend and multi-graph figures were visually inspected. Report snapshots retained goals and dots. JavaScript syntax, ZIP integrity and byte-identical root/standalone HTML were verified. No full-browser layout run was performed.

Version/build and current help identify v71. All unrelated v70 features, including menus/carets, exclusive panel categories, Report Insert, live data, fractions, ratings, cloud darkness/plain classroom points, one-sided analyses, grids, session mapping and exports, remain in the SCGraph2 framework.
