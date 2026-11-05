# Fuzzy PI Control for bittide - ACM working manuscript

## Current draft

The main paper preserves the author's title and author block and uses the
original `\documentclass[sigconf]{acmart}` layout. Sections 1, 3 and 4 are
integrated from the approved 2026-11-02 v3 package. ACM default section
numbering, typography and margins are retained.

Background (2), Evaluation (5), Discussion (6), Conclusion (7), the abstract,
acknowledgments, CCS and publication metadata remain pending or provisional.
The Introduction summarizes existing approved experiments; the Evaluation
section has not yet incorporated their full evidence. This is a working
manuscript, not a completed submission.

## Build in VS Code

Open this entire folder in VS Code with LaTeX Workshop. Save `main.tex` or
press Ctrl+Alt+B to compile, and Ctrl+Alt+V to preview.

```powershell
latexmk -pdf -synctex=1 -interaction=nonstopmode -file-line-error main.tex
```

The authoritative current output is **`main.pdf` in this project root**,
matching the latest pre-integration build convention. Both `.latexmkrc`
and the project VS Code settings use that location. The old `build/main.pdf`
is archived with the pre-integration backup; do not use it as the current
manuscript. Auxiliary files are left beside the root output.

## Source map

- `main.tex`: ACM metadata, title/authors, abstract and section inputs.
- `sections/introduction.tex`: LaTeX adaptation of Introduction v5.
- `sections/section_iii_paper.tex`: complete proposed controller and analysis.
- `sections/section_iv_paper.tex`: fluid-reference certificate and margins.
- `bittide_math_preamble.tex`: theorem definitions reusing ACM packages.
- `references.bib`: four public bittide works; no internal report citation.
- `author_notes/`: preserved author opening and original Introduction v5.
- `INTEGRATION_NOTES_zh.md`: merge decisions, provenance and backup details.

The original two-page template and its example equation, figure, table and
LaTeX-book reference are preserved in the full backup. Figures belong in
`images/`. Do not change ACM margins or font sizes to meet a page limit.
