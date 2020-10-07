# GiB Thesis LaTeX Template
>LaTeX template for theses (i. e. dissertation) at the Chair of Geotechnical Engeneering at RWTH Aachen.
The template is based on the *scrbook-class* of the *KOMA-Script*. Some design modifications are made to match the design demands of the chair:
* fontsize
* margins
* linespacing
* header/footer
* citation
* headgins (chapter/section/subsection)
* captions (tables and figures)

[![License: GNU](https://img.shields.io/github/license/froido/gib-latex-template?style=flat-square)](LICENSE)
[![License: GNU](https://img.shields.io/github/release-date/froido/gib-latex-template?style=flat-square)](https://github.com/froido/gib-latex-template/releases)
[![License: GNU](https://img.shields.io/github/v/release/froido/gib-latex-template?style=flat-square)](https://github.com/froido/gib-latex-template/releases)
[![MiKTeX](https://img.shields.io/static/v1?label=MiKTeX&message=v20.7&color=5269A9&style=flat-square&logo=latex)](https://miktex.org/)
[![MiKTeX](https://img.shields.io/static/v1?label=MiKTeX&message=PdfLaTeX&color=5269A9&style=flat-square&logo=latex)](https://miktex.org/)
[![KOMA-Script](https://img.shields.io/static/v1?label=KOMA-Script&message=v3.31&color=5269A9&style=flat-square&logo=latex)](https://komascript.de/)
	
---

## Requirements
[![MiKTeX](https://img.shields.io/static/v1?label=MiKTeX&message=v20.7&color=5269A9&style=flat-square&logo=latex)](https://miktex.org/)
[![MiKTeX](https://img.shields.io/static/v1?label=MiKTeX&message=PdfLaTeX&color=5269A9&style=flat-square&logo=latex)](https://miktex.org/)
[![KOMA-Script](https://img.shields.io/static/v1?label=KOMA-Script&message=v3.31&color=5269A9&style=flat-square&logo=latex)](https://komascript.de/)  
This template is coded to be compiled with *PdfLaTeX*. Other compilers like *XeLaTex* or *LuaLaTeX* can cause unpredictable errors. The continuous development of *KOMA-Script*, *MiKTeX* and other packages may lead to some commands being deprecated or to packages no longer being compatible with each other. The template was developed for the following packages and the announced specific version.

* MiKTeX v20.7
* KOMA-Script v3.31

*Other required packages are listed under the topic __Packages__.*

---

## Usage

1. Include `designGiB.tex` to your main document:
  ```tex
  \input{designGiB}
  ```

2. Optional: Load additional packages.

3. Setup user defined values like *title* or *author* via:
   ```tex
   \newcommand*{\myTitle}{My extravagant dissertation title}  % thesis title
   \newcommand*{\myAuthor}{Jane Doe}  % authors name
   ```
   *Find additional information in __Data input for headings and title page__.*  
 
4. Optional: Include bibliography and acronym sources.
   ```tex
   \input{acronyms}  % acronyms.tex contains acronyms definitions
   \addbibresource{bibliography.bib}  % bibliography.bib is a BibLaTeX file
   ```
  
5. Begin the document.
   ```tex
   \begin{document}
   ...
   \end{document}
   ```
  
6. Include a specific title page, e. g. `titlepage_dissertation_de`
   ```tex
   \input{../../design-template/titlepage_dissertation_de}
   ```
7. Remember to use `/frontmatter`, `/mainmatter` and  `/appendix`. *(see Additional Hints|Document segmantation)*

8. Start your thesis!

---

## Structure
This repository constits of a design template, title pages (different per thesis type) and samples (minimal and full).

├── [design-template/](design-template)  
│&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;├── designGiB.tex `design template`  
│&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└── titlepage_dissertation_de.tex `title page for dissertation in german`  
└── samples/  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;├── [minimal/](samples/minimal) `folder containing a minimal sample`  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;├── bibliography.bib `contains the bibliography`  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;├── content.tex `this file contains all content`  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;├── main.tex `merges everything together, sets language, sets user variables`  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└── main.pdf `final document`  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└── [full/](samples/full) `folder containing a full sample (with german remarks)`  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;├── chapter/ `folder containing the thesis content`  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;├── figures/ `folder containing all figures`  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;├── bibliography.bib `contains the bibliography`  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;├── content.tex `this file contains all content`  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;├── main.text `merges everything together, sets language, sets user variables`  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└── main.pdf `final document`  

---

## Packages
### Mandatory packages
* `acro` handles acronyms
* `amsmath` improves the math mode and is strongly recomended when working with equations
* `biblatex` handels citations with BibLaTeX __not__ BibTeX
* `csquotes` provides advanced facilities for inline and display quotations
* `fontenc` mandatory for correct encoding of western european letters
* `geometry` is used to change margins
* `lmodern` changes fonts and makes them clearer
* `longtable` table enrivonment for tables longer then a single page (in this case its used list of symbols)
* `scrlayer-scrpage` is part of KOMA-script and is used to manipulate header and footer, i. e. adding seperation lines
* `setspace` changes the linespacing in an easy way
* `textcomp` modifies symbols, i. e. § and €

### Recommended packages
* `booktabs` adds and changes lines and spacing in tables and beautifies them
* `graphicx` used to include graphics
* `hyperref` modifies links and refs in generated pdf (in this case links are not shown)
* `textalpha` makes it possible to use greek letters in the source code instead of using functions like `$\alpha$`
* `lineno` creates line numbering which is usefull for a review process
* `siunitx` helpfull to show value-unit-pairs in text
* `todonotes` insert to–do items in your document
* `pdfpages` include full pdf documents (not only single pages like includegraphics)
* `tabularx` create tabulars with a fixed width (one flexible col)


### Recommended packages for germans
* `babel` sets the documents language
* `ziffer` activates the german punctation conversion: `,` is decimal separator; `.` is thousand separator (will be replaced by protected space)

---

## Data input for headings and title page
Different title pages are available (shall be) depending on the type of thesis. To create the title page some additional information are needed. The kind of information depends on the title page. The information have to be written into commands, that are going to be used by the title page, e. g. `\newcommand*{\myAuthor}{Jane Doe}`. In addition the heading for list of acronyms and the bibliography and the footer content can be modified.

* `\myTitle` title of the thesis
* `\mySubtitle` subtitle of the thesis
* `\myAuthor` author of the thesis
* `\myFirstReviewer` first reviewer or examiner
* `\mySecondReviewer` second reviewer or examiner
* `\myExamDate` date of the presentation or submission
* `\myFootText` text shown in the footer
* `\myAcronymListCaption` chapter caption for list of acronyms
* `\myBibCaption` chapter caption for bibliography

---

## Additional Hints
### Setup template to German language
1. Include packages `babel` and `ziffer`
   ```tex
   \usepackage[ngerman]{babel}  % set language to german
   \usepackage{ziffer}  % conversion of punctuation in maths mode (switches . and ,)
   ```
2. Change headings for list of acronyms and bibliography:
   - Setting user defined names
     ```tex
     \newcommand*{\myAcronymListCaption}{Abkürzungsverzeichnis}
     \newcommand*{\myBibCaption}{Literaturverzeichnis}
     ```
   - Set acronyms heading *before* starting the document with `\begin{document}`
     \acsetup{list/name={\myAcronymListCaption}}
   - When calling `\printbibliography` set option to `title={\myBibCaption}`
     ```tex
     \printbibliography[title={\myBibCaption}]
     ```

### Document segmantation
1. Use `\frontmatter` at the beginning and set the page numbering to *Roman*. The front matter includes all lists of something, e. g. figures, table of contents and titlepage.
   ```tex
   \frontmatter
   \pagenumbering{Roman}
   ... (title page, list of...)
   ```
   
2. Following use `\mainmatter` for the main part of the document, closing with the bibliography.

3. Close the document with `\appendix`.
   ```tex
   \appendix
   \clearpage
   
   ... your appendix content
   
   \end{document}
   ```

### Easy Review
1. Include package `lineno`
   ```tex
   \usepackage{lineno}
   ```
2. Put the following code at the beginning of your document
   ```tex
   \begin{document}
     \linenumbers  % add numbers to each line
     \setstretch{2}  % set line spacing to factor 2
   ...
   ```

### Preset default figures path
You can preset a default path where figures are stored to reduce typing in your main document.
Set default path via
```tex
\graphicspath{{figures/}}
```
Now you can use 
```tex
\includegraphics{yourFigure.jpg}
```
instead of
```tex
\includegraphics{figures/yourFigure.jpg}
```

### Create a list of symbols
The easiest way to create a list of symbols is to create a table containing your symbols and the description. You should use a longtable in this case to be prepared for a table enlarging a single page.

```tex
\chapter{List of Symbols}
  \section*{Latin Letters}
    \begin{longtable}[l]{p{1cm}p{1cm}l}
      $A_0$ & $[m^2]$ & cross-sectional area at the beginning of the experiment \\
      $B$ & $[m]$ & Sample width\\
      ...
    \end{longtable}
```

### Use value-unit-pairs (siunitx)
To create a value unit pair the opportunities of siunitx package should be used. 

```tex
\SI{35}{\kilo\newton\per\square\meter}  % single value
\SIrange{1e-9}{10e-9}{\meter\per\second}  % range inlcuding value
```


### Captions for tables
To create a caption above a table, respecting design margings `\captionabove` must be used instead of `\caption`.

```tex
\begin{table}
  \captionabove{Your table caption}
  \label{tbl:yourTableName}
  \centering
  \begin{tabular}{lrr} 
    % content
  \end{tabular}
\end{table}
```

---

## Support

Reach out to me at one of the following places!

- Website at <a href="http://www.geotechnik.rwth-aachen.de/index.php?section=Biebricher_en" target="_blank">`www.geotechnik.rwth-aachen.de`</a>
- <a href="https://orcid.org/0000-0001-9018-3485" target="_blank">ORCID</a>
- <a href="https://www.xing.com/profile/SvenF_Biebricher" target="_blank">XING</a>

---

## License

[![License: GNU](https://img.shields.io/github/license/froido/gib-latex-template?style=flat-square)](LICENSE)  
This project is licensed under the GNU General Public License v3.0 - see the [LICENSE](LICENSE) file for details

---
