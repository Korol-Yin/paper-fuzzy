# ACM ten-page main text and appendices

The ACM sigconf class, default fonts, margins and two-column layout are retained.

- Main text (title/abstract through Conclusion): pages 1-10.
- References: page 11.
- Appendices: pages 12-30.
- A: Extended Background, corresponding to main Section 2.
- B: Complete controller realization, calibration, rule and nonlinear derivations, corresponding to Section 3.
- C: Full stability/safety proofs, witness arithmetic, interval prefix and tail, corresponding to Section 4.
- D: Full experiment protocol, replay/metric definitions and supplementary figures/results, corresponding to Section 5.
- E: Extended interpretation and limitations, corresponding to Section 6.

Each appendix has an explicit linked correspondence line. Internal detailed labels use their own namespace.
The original long manuscript, abstract, figures and PDF were fully backed up before restructuring.
The final source and PDF have a separate backup. Paths and SHA256 values are in the companion JSON.

Core retained in the main text: full 25-rule definition/table, PI calibration, regional nonlinear map,
joint safety constraints, parameter relationships, strict headroom theorem, matched-gain startup
results, frozen gains, untouched paired effects, both held-out burst outcomes and a concise scope
statement including slow-delivery confirmation. No experiment data or old figures were deleted.

Local pdfLaTeX/BibTeX compilation and all source/cross-reference checks passed. No overfull boxes remain.
Thirty pages were rendered for visual QA. The ACM class emits its automatic final-column balance warning;
this is not a source error. The built-in preview helper remains unavailable due to Windows sandbox preparation.

Venue/author/CCS metadata are still draft placeholders. No claim of submission readiness is made.
