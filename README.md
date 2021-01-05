# GiB Thesis LaTeX Template
>LaTeX template for theses (i. e. dissertation) at the Chair of Geotechnical Engeneering at RWTH Aachen.
The template is based on the *scrbook-class* of the *KOMA-Script*. Some design modifications are made to match the design demands of the chair:
* fontsize
* margins
* linespacing
* header/footer
* citation
* headings (chapter/section/subsection)
* captions (tables and figures)
* title page

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
* Babel v3.51

*Other required packages are listed under the topic __Packages__.*

---

## Usage

0.  Include the biblatex citation and bibliography styles.
    This can be done in two different ways:
    1. Add the *texmf* folder (in biblatex-style) to your miktex installation:
        1. Open *Miktex Console* 
        2. Select Operation Mode
        3. Goto *Settings > Directories > Add*
        4. Choose *texmf* folder from *./biblatex-style* folder
        5. *Task > Refresh file name database*
        6. You are good to go
        
    2. Copy the files rwth-gib.bbx and rwth-gib.cbx contained in one of the subfolders to the root directory of your document (same folder where main.tex is stored).
    
    *It is highly recomended to choose the first solution, as an update to a newer version of this repo is much easier and less confusing.*
        
1.  Include `designGiB.tex` to your main document:
  ```tex
  \input{designGiB}
  ```

2.  Optional: Change language from english to ngerman in document class. This needs to be hardcoded into the designGiB!

3.  Setup user configuration file `user_config.tex` in subfolder `./additionals`.
    You must not include this file, this is automatically done by the template.
    1.  Set document `\def\myThesisType{xx}` type BA for bachelor thesis, MA for master thesis or DISS for dissertation:
    2.  Set author, reviewers/examiners and exam date 		
        ```tex
        \def\myAuthor{Your Name}
        \def\myFirstReviewer{First Reviewer}
        \def\mySecondReviewer{Second Reviewer}
        \def\myExamDate{30.02.2021}
        ```
    3. Setup additional information like title/subtitle (for dissertation) or german/english title, supervisor and location (for master/bachelor thesis).
		```tex
        % dissertation
		\def\myTitle{Dissertation Title}
		\def\mySubtitle{Subtitle for Dissertation}
		
        % bachelor/master thesis
		\def\myTitleDe{Deutscher Titel der Arbeit}
		\def\myTitleEn{English Thesis Title}
		\def\mySupervisor{Supervisors Name}
		\def\myExamLocation{Location}
        ``` 
        *Find additional information in __Data input for headings and title page__.*  
  
    4. Optional: Load additional packages
    
4. Optional: Include bibliography and acronym sources in `main.tex` not in `user_config.tex`.
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
  
6. Include a specific title page (automatically set by template)
   ```tex
   \input{../../design-template/\myTitlepage}
   ```
7. Remember to use `/frontmatter`, `/mainmatter` and  `/appendix`. *(see Additional Hints|Document segmantation)*

8. Start your thesis!

---

## Structure
This repository consists of a design template, title pages (different per document type), a bibliography style and samples (minimal and full).

├── [design-template/](design-template)  
│&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;├── designGiB.tex `design template`  
│&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;├── titlepage_dissertation_de.tex `title page for dissertation in german`  
│&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└── titlepage_bachelor_master.tex `title page for master/bachelor thesis language independend`  
├── [biblatex-style/](biblatex-style)   
│&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└── [texmf/tex/latex/biblatex/](biblatex-style/texmf/tex/latex/biblatex)   
│&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;├── [bbx/](biblatex-style/texmf/tex/latex/biblatex/bbx)   
│&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└── rwth-gib.bbx `biblatex bibliography style`  
│&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└── [cbx/](biblatex-style/texmf/tex/latex/biblatex/cbx)   
│&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└── rwth-gib.cbx `biblatex bibliography style`  
└── samples/  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;├── [minimal/](samples/minimal) `folder containing a minimal sample`  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;├── bibliography.bib `contains the bibliography`  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;├── content.tex `this file contains all content`  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;├── main.tex `merges everything together, sets language, sets user variables`  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└── main.pdf `final document`  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└── [full/](samples/full) `folder containing a full sample (with german remarks)`   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;├── additionals/ `folder containing additional content like user_config.tex, bibliography and acronyms.`   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;├── chapter/ `folder containing the thesis content`  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;├── figures/ `folder containing all figures`      
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;├── main.text `merges everything together, sets language, sets user variables`  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└── main.pdf `final document (compiled)`  

---

## Packages
All up-coming packages, with the exception of the packages recommended for Germans, are already set up in the template.
### Mandatory packages
* `acro` handles acronyms
* `amsmath` improves the math mode and is strongly recomended when working with equations
* `babel` sets the documents language
* `biblatex` handels citations with BibLaTeX __not__ BibTeX
* `caption`  additional options for captions and required for subcaption package
* `csquotes` provides advanced facilities for inline and display quotations
* `enumitem` improves enumerate and itemize environment
* `fontenc` mandatory for correct encoding of western european letters
* `geometry` is used to change margins
* `lmodern` changes fonts and makes them clearer
* `longtable` table enrivonment for tables longer then a single page (in this case its used list of symbols)
* `microtype` better results in line breaks and overfull boxes 
* `scrlayer-scrpage` is part of KOMA-script and is used to manipulate header and footer, i. e. adding seperation lines
* `setspace` changes the linespacing in an easy way
* `subcaption` includes subfigure environment
* `textcomp` modifies symbols, i. e. § and €
* `uarial` use an arial-cloned font as ssfamily font
* `xcolor` makes latex more colorful and is needed to create title pages

### Recommended packages
* `booktabs` adds and changes lines and spacing in tables and beautifies them
* `enumitem` modifies and extends enumerate and itemize environment
* `graphicx` used to include graphics
* `hyperref` modifies links and refs in generated pdf (in this case links are not shown)
* `lineno` creates line numbering which is usefull for a review process
* `lscape` introduce landscape environment, for exmaple to turn tables
* `pdfpages` include full pdf documents (not only single pages like includegraphics)
* `siunitx` helpfull to show value-unit-pairs in text
* `tabularx` create tabulars with a fixed width (one flexible col)
* `textalpha` makes it possible to use greek letters in the source code (unicode) instead of using functions like `$\alpha$`
* `todonotes` insert to–do items in your document

### Recommended packages for germans
* `ziffer` activates the german punctation conversion: `,` is decimal separator; `.` is thousand separator (will be replaced by protected space)

---

## Data input for headings and title page
Different title pages are available depending on the document type.
To create a nice and correct title page some additional information are needed and the kind of intermation depends on the title page.
The information have to be written into commands, that are going to be used by the title page, e. g. `\def{\myAuthor}{Jane Doe}`.
These additional information have to be stored in a seperate file called `user_config.tex` stored in `additional` subfolder (see full sample).

* `\myThesisType` type of document: BA, MA or DISS
* `\myAuthor` author of the document
* `\myFirstReviewer` first reviewer or examiner
* `\mySecondReviewer` second reviewer or examiner
* `\myExamDate` date of the presentation or submission

Additional for dissertation:
* `\myTitle` title of the thesis
* `\mySubtitle` subtitle of the thesis

Additional for bachelor/master thesis:
* `\myTitleDe` title of thesis in german
* `\myTitleEn` title of thesis in english
* `\mySupervisor` name of supervisor
* `\myExamLocation` location of the examination, i. e. Aachen

---

## Additional Hints
### Setup template to German language
1. Modify language in template `designGiB`.
    Change `english` to `ngerman` as follows from
    ```tex
    \documentclass[	paper=a4,  % paper size set to DIN A4
                    [...]  % some options are left out here for a better overview!
                    % set language that will be send to all language dependend packages, e.g. babel
                    english  % set language to english
                    % ngerman  % set language to new german
                  ]{scrbook}  % document class
    ```
    to
    ```tex
    \documentclass[	paper=a4,  % paper size set to DIN A4
                    [...]  % some options are left out here for a better overview!
                    % set language that will be send to all language dependend packages, e.g. babel
                    % english  % set language to english
                    ngerman  % set language to new german
                  ]{scrbook}  % document class
    ```

   
1. Include package `ziffer`
   ```tex
   \usepackage{ziffer}  % conversion of punctuation in maths mode (switches . and ,)
   ```

3. Change headings for bibliography:
   - When calling `\printbibliography` set option to `title={\myBibCaption}`
     ```tex
     \printbibliography[title={\myBibCaption}]
     ```

### Error(s) while compiling
If you are running into errors while compiling your latex document, these hints might help you to solve your problem:
1. Update your miktex installation to prevent errors due to oudated packages.
2. Check if compiler is set to *PdfLaTeX* and _not_ *XeLaTex* or *LuaLaTeX*.
3. Check if bibliography interpreter is set to *biber* (biblatex) but not to *bibtex*
4. Take a deeper look into the log files and try to solve it on your own.
5. Running on Linux? Inlcude `inputenc` package and set option to *utf8*.


### Bibliography
Set up/declare the bibliography file `*.bib` in your main document and not in the `user_config.tex`. Due to the software you are using this can cause problems, because the software, e.g. TeXstudio, doesn't recognize the bibliography files, doesn't run biber and therefore the compiler tells you, that `main.bbl` is missing. Furthermore will the bibliography compiling not be done automatically, as changes of the bibliography file are not automatically recognized by your software.

### Document segmantation
1. Insert the title page before the frontmatter starts to ensure the start of page numbering at the TOC.

1. Use `\frontmatter` at the beginning and set the page numbering to *Roman*. The front matter includes all lists of something, e. g. figures and table of contents.
   ```tex
   \frontmatter
   \pagenumbering{Roman}
   ... (title page, list of...)
   ```
   
2. Following use `\mainmatter` for the main part of the document, closing with the bibliography. In this and the upcomming parts page numbering is set so *arabic* automatically.

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
The easiest way to create a list of symbols is to create a table containing your symbols and the description. You should use a longtable in this case to be prepared for a table enlarging a single page. Each column has a fixed width to ensure linebreaks if a description is to long for a single line.

```tex
\chapter{List of Symbols}
  \section*{Latin Letters}
    \begin{longtable}[l]{p{1.5cm}p{1.5cm}p{0.7\linewidth}}
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
