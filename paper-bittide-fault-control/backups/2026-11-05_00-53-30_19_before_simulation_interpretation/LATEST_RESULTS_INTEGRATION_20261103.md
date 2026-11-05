# Latest simulation integration (2026-11-03)

The active Evaluation now uses the completed equal-budget selection, independent tests,
slower-delivery study and matched-gain safety stress. Introduction and Abstract are synchronized.

- All previous Evaluation text is retained as line comments at the end of evaluation.tex.
  Legacy fixed-preset tables and figures no longer compile. Raw evidence is unchanged.
- The active text emphasizes positive conditional results. It retains concise reporting of
  directly relevant confirmation boundaries, both registered held-out bursts and common-frequency
  costs so that the positive claim does not imply superiority across all completed tests.
- Matched-gain startup/reference findings and separately tuned test representatives are distinguished.
- Actual startup horizon is the locked 2001H (~2.001067e6) ticks, not 4e6. This departure from
  the earlier broad instruction is disclosed. No claim of a 4e6 safety record is made.
- No new simulations, PDF figures, or standalone PDF documents were produced. Existing verified
  PNG/SVG assets are copied with hashes. Built-in editor compilation will check the updated project.
- Discussion/Conclusion and author/conference metadata remain separate pending writing tasks.

Sources and hashes: latest_results_provenance_20261103.json; copied numeric evidence under
evidence/latest_results_20261103. Full raw data remain in the original simulation directories.

## Final verification

- Built-in editor compilation was attempted but its Windows sandbox helper could not prepare the preview.
- Local pdfTeX draft mode (three passes) and BibTeX passed, with no undefined references or citations.
- No PDF was generated; the existing main.pdf was unchanged during validation.
- New prose line overflows were repaired. Remaining line overflows are in unchanged Background/III/IV;
  minor page-box warnings remain. No rendered preview validation is claimed.
- Source structure: 9 TeX inputs, 133 unique labels, 30 distinct referenced labels, 4 valid bibliography keys.
- Third/fourth-section derivations and Background are hash-identical to the pre-update backup.
- A final source snapshot is recorded in latest_results_provenance_20261103.json.
