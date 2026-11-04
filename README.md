# CV

Two CVs built from shared sources:

- `denovellis-cv.tex`: academic CV (full publication list, talks, abstracts).
- `denovellis-cv-neurotech.tex`: industry CV, must stay at 2 pages (CI checks this).

Publications live in `publications.bib` (papers, preprints) and `abstracts.bib`
(conference abstracts, academic CV only), formatted by `cvbib.sty`.
`res.cls` is a locally modified copy of the resume class.

## Build

```sh
latexmk          # builds both PDFs (pdflatex + biber); see latexmkrc
latexmk -c       # remove intermediate files
```

On Overleaf, upload all six source files together (`*.tex`, `res.cls`,
`cvbib.sty`, `*.bib`); mixing old and new versions of `res.cls` and
`cvbib.sty` breaks the build.

## CI

`.github/workflows/build.yml` builds both PDFs on every push and pull request;
download them from the run's `cv-pdfs` artifact.
