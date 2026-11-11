# Academic CV template

A compact LaTeX template with small-caps section headings, right-aligned dates, and sections for research, teaching, and academic service. [View the two-page example](cv.pdf).

## Get started

1. Download `cv.tex` and `academiccv.sty` into the same folder, or download the repository ZIP.
2. Open `cv.tex` and replace the fictional sample content. Add, remove, or reorder sections as needed.
3. Compile with pdfLaTeX. In Overleaf, upload both files and select `cv.tex` as the main document. Locally, run the following from the project folder with a LaTeX installation that includes `latexmk` and the required packages.

   ```sh
   latexmk -pdf cv.tex
   ```

   The output is `cv.pdf`. Use `latexmk -g -pdf cv.tex` to refresh the date without editing the source. You can also run `pdflatex cv.tex` twice if `latexmk` is unavailable.

## Edit your CV

| Command | Use |
| --- | --- |
| `\cvheader[Month Year]{Name}{Affiliation and address}{Contacts}` | Use `\\` for line breaks inside the last two fields. Use `\cvcurrentmonth` for the month and year at compile time, or omit the square brackets to hide the date. |
| `\section{Heading}` | Start a section. |
| `\cventry{Title}{Details}{Dates}{Date note}` | Add a degree, job, talk, or award. Use `{}` for unused fields. Use `\par` for another line in the details. |
| `\cvpublication{Title}{Citation and links}` | Add a publication or working paper. The template inserts a period after the title. |
| `\cvsubheading{Label}` | Add an italic group label within a section. |
| `\cvtext{Text}` | Align a text entry with the main entry column. |
| `\cvdetail{Label}{Details}` | Add a two-column row for skills or languages. |

Use `\href{URL}{Link text}` for a website or DOI and `\href{mailto:address}{Address}` for email. Use `\cvsep` to separate links with a small bullet. Escape special characters in ordinary text, such as `\&` and `\%`.

The layout is in `academiccv.sty`. To use US Letter, change `a4paper` to `letterpaper` on the first line of `cv.tex`. The Source Serif Pro font comes from the LaTeX package `sourceserifpro`. The version date uses `datetime2` and its English language module.

## License

The template and example are available under the [MIT License](LICENSE).
