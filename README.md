# Academic CV template

A compact LaTeX template with small-caps section headings, right-aligned dates, and sections for research, teaching, and academic service. [View the two-page example](cv.pdf).

## Get started

1. Download the repository ZIP, or keep `cv.tex`, `academiccv.sty`, `academiccv.bst`, and `publications.bib` together in one folder.
2. Open `cv.tex` and replace the fictional sample content. Edit publication details in `publications.bib`. Add, remove, or reorder sections as needed.
3. In Overleaf, upload the source files and select `cv.tex` as the main document with the pdfLaTeX compiler. For a local LaTeX installation, run the following from the project folder.

   ```sh
   latexmk -pdf cv.tex
   ```

   This runs pdfLaTeX and classic BibTeX as needed and writes `cv.pdf`. Use `latexmk -g -pdf cv.tex` to refresh the date without editing the source.

   You can also run the build steps directly.

   ```sh
   pdflatex cv.tex
   bibtex cv
   pdflatex cv.tex
   pdflatex cv.tex
   ```

## Publications from a BibTeX file

The sample uses standard BibTeX fields and includes the complete author list.

```bibtex
@article{mccaffrey2007studio,
  author  = {McCaffrey, Piers and Morton, Glen and Ellery, Gus},
  title   = {A Day in the Studio},
  journal = {Four-Track Review},
  year    = {2007},
  url     = {https://example.org/day-in-the-studio}
}
```

Separate authors with `and`. Use TeX accent commands for accented names, and braces around title text whose capitalization should be preserved, such as `{UK}`.

The publication section in `cv.tex` contains the following commands.

```latex
\nocite{*}
\bibliographystyle{academiccv}
\bibliography{publications}
```

The asterisk includes every entry in the file. To select entries, use their keys, for example `\nocite{mccaffrey2007studio,mccaffrey1995fragment}`. Entries are sorted newest first. The style supports the standard BibTeX entry types, including articles, books, chapters, conference papers, reports, and theses.

Optional fields include `doi`, `url`, and `eprint`. Use a DOI identifier such as `10.1234/example` in `doi`. An `eprint` identifier links to arXiv, and a full URL links directly to the preprint. For a separately linked working-paper version, use a URL in `eprint` with `eprinttype = {workingpaper}`.

To link an author's profile, add a mapping in the preamble of `cv.tex`.

```latex
\cvbiblink{Jim}{Lemon}{https://example.org}
```

The first two arguments match the given and family names in the bibliography. The sample profile links use `example.org`.

You can also type a publication directly with `\cvpublication{Title}{Citation and links}`. For a fully manual publication list, replace the three bibliography commands with your manual entries. The manual command works with `academiccv.sty` alone.

## Edit your CV

| Command | Use |
| --- | --- |
| `\cvheader[Month Year]{Name}{Affiliation and address}{Contacts}` | Use `\\` for line breaks inside the last two fields. Use `\cvcurrentmonth` for the month and year at compile time, or omit the square brackets to hide the date. |
| `\section{Heading}` | Start a section. |
| `\cventry{Title}{Details}{Dates}{Date note}` | Add a degree, job, talk, or award. Use `{}` for unused fields. Use `\par` for another line in the details. |
| `\cvpublication{Title}{Citation and links}` | Type a publication directly. The template inserts a period after the title. |
| `\cvsubheading{Label}` | Add an italic group label within a section. |
| `\cvtext{Text}` | Align a text entry with the main entry column. |
| `\cvdetail{Label}{Details}` | Add a two-column row for skills or languages. |

Use `\href{URL}{Link text}` for a website or DOI and `\href{mailto:address}{Address}` for email. Use `\cvsep` to separate links with a small bullet. Escape special characters in ordinary text, such as `\&` and `\%`.

The layout is in `academiccv.sty`, and the BibTeX formatting is in `academiccv.bst`. To use US Letter, change `a4paper` to `letterpaper` on the first line of `cv.tex`. The Source Serif Pro font comes from the LaTeX package `sourceserifpro`. The version date uses `datetime2` and its English language module.

## License

The CV template and sample are available under the [MIT License](LICENSE). The bibliography style is adapted from the standard `plain.bst` and includes its original copyright and redistribution notice.
