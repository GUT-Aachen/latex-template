# GiB Thesis LaTeX Template
LaTeX template for theses (i.e. dissertation) at the Chair of Geotechnical Engeneering at RWTH Aachen.
The template is based on the scrbook-class of the KOMA-Script. Some design modifications are made to match the design demands of the chair:
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
[![MiKTeX](https://img.shields.io/static/v1?label=LaTeX&message=MiKTeX&color=5269A9&style=flat-square&logo=latex)](https://miktex.org/)
[![KOMA-Script](https://img.shields.io/static/v1?label=LaTeX&message=KOMA-Script&color=5269A9&style=flat-square&logo=latex)](https://komascript.de/)

---

## Structure
This repository constits of a design template, titlepages (different per thesis type) and samples (minimal and full).

├── [design-template/](design-template)  
│&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;├── designGiB.tex `design template`  
│&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└── titlepage_dissertation_de.tex `titlepage for dissertation in german`  
└── samples/  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;├── [minimal/](samples/minimal) `folder containing a minimal sample`  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;├── bibliography.bib `contains the bibliography`  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;├── content.tex `this file contains all content`  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└── main.text `merges everything together, sets language, sets user variables`  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└── [full/](samples/full) `folder containing a full sample (with german remarks)`  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;├── chapter/ `folder containing the thesis content`  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;├── figures/ `folder containing all figures`  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;├── bibliography.bib `contains the bibliography`  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;├── content.tex `this file contains all content`  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└── main.text `merges everything together, sets language, sets user variables`  

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
* `scrlayer-scrpage` is part of KOMA-script and is used to manioulate header and footer, i.e. adding seperation lines
* `setspace` changes the linespacing in an easy way
* `textcomp` modifies symbols, i.e. § and €

### Recommended packages
* `booktabs` adds and changes lines and spacing in tables and beautifies them
* `graphicx` used to include graphics
* `hyperref` modifies links and refs in generated pdf (in this case links are not shown)
* `textalpha` makes it possible to use greek letters in the source code instead of using functions like `$\alpha$`
* `lineno` creates line numbering which is usefull for a review process


### Recommended packages for germans
* `babel` sets the documents language. Option `[german]` for german.
* `ziffer` activates the german punctation conversion: `,` is decimal separator; `.` is thousand separator (will be replaced by protected space)

---

## Data input for headings and title page
Different title pages are available (shall be) depending on the type of thesis. To create the title page some additional information are needed. The kind of intermation depends on the titlepage. The information have to be written into commands, that are going to be used by the title page, i.e. `\newcommand*{\myAuthor}{Jane Doe}`. In addition the heading for list of acronyms and the bibliography and the footer content can be modified.

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
