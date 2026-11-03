# UPenn PhD Dissertation LaTeX Style

The `upennstyle.sty` file in this repository takes the official LaTeX template
and cleans it up by removing unnecessary packages, deleting most comments, and fixing spacing and indentation.
It also introduces a few convenience macros and adds some opinionated styling,
which (hopefully) are all within the regulations of the dissertation format.

Unfortunately, the dissertation formatting guide is a gross and disgusting DOCX file,
so a PDF version of it is included in this repository.
The pre-deposit checklist PDF is also included for convenience.

## Packages

This style file requires the following packages:

* `geometry` for setting margins;
* `setspace` for double spacing;
* `parskip`  for paragraph spacing;
* `tocloft`  for adusting the table of contents;
* `titlesec` for styling titles; and
* `hyperref` for hyperlinks.

The packages that have been removed from the original file are
`babel`, `csquotes`, `amsthm`, `amsmath`, `amssymb`, `amsfonts`, `amscd`, `calc`, `graphicx`, `float`,
`caption`, `multirow`, `blindtext`, `fancyvrb`, `appendix`, `array`, `tabularx`, `booktabs`, `pdflscape`.
Many of these are desirable to have but you'll have to add them yourself.

## Macros

The following macros are for filling out your information in the preamble and each take one argument.

| Macro                | Description |
| -------------------- | ----------- |
| `\gradgroup`         | Graduate group |
| `\specialization`    | Specialization (Wharton MSAE and SAS FIGS only) |
| `\supervisor`        | Supervisor full name only |
| `\supervisortitle`   | Full professorship title ("... Professor of ...") |
| `\cosupervisor`      | Cosupervisor full name only (optional) |
| `\cosupervisortitle` | Full professorship title (optional) |
| `\gradchair`         | Graduate chairperson full name **and** title |
| `\committee`         | Committee member full name **and** title (**and** affiliation if external) (one for each member) |
| `\authorlegal`       | Your full legal name for the copyright notice |
| `\cclicense`         | Creative Commons license; [choose license here](https://creativecommons.org/chooser/) (optional) |
| `\cclicenseurl`      | Creative Commons license URL; [find licenses here](https://creativecommons.org/licenses/) (optional) |
| `\dedication`        | Dedication text (optional) |
| `\acknowledgements`  | Acknowledgements text (optional) |
| `\abstract`          | Abstract text |
| `\preface`           | Preface text (optional) |

There is also a 🆕 `\titlefamily` macro that you can renew to change the font family of
chapter titles (default: `\rmfamily`),
and a 🆕 `\secfamily` macro for the font family of
section, subsection, and paragraph titles (default: `\bfseries\sffamily`).

The following macros go in the `document` environment and actually print out the above pages.

```tex
\usepackage{upennstyle}

% above preamble content goes here

\begin{document}

\maketitle \setcounter{page}{2}
\makecopyright        % optional; pick only one of this and \makecreativecommons
\makecreativecommons  % optional; pick only one of this and \makecopyright
\makededication       % optional
\makeacknowledgements % optional
\makeabstract
\tableofcontents
\makelot              % 🆕 optional if there are no tables
\makelof              % 🆕 optional if there are no figures
\makepreface

\begin{mainf}
% dissertation chapters go here
\end{mainf}

\begin{append}
% optional appendices go here
\end{append}

\begin{bibliof}
% bibliography goes here
% \printbibliography if using biblatex
%   (with \addbibresource{bib file name.bib} in preamble)
% \bibliography{bib file name} if using natbib
\end{bibliof}

\end{document}
```

## Styling changes

* "ACKNOWLEDGEMENT" renamed to "ACKNOWLEDGEMENTS"
* "LIST OF ILLUSTRATIONS" renamed to "LIST OF FIGURES"
* "BIBLIOGRAPHY" renamed to "REFERENCES"
* Supervisor, grad chair, and committee are flush to bottom of title page
* Blank lines between supervisor, grad chair, and committee
* Dissertation committee members are single-spaced
* Creative Commons license notice only has one linebreak per sentence
* Chapter numbers in table of contents no longer followed by ":"
* Chapters (and appendices) no longer begin with "CHAPTER" (or "APPENDIX");
  there is a 1.5 em space between the chapter number (or appendix letter) and the title
* Section and subsection numbers no longer end with "."
* Minor title spacing adjustments

## Resources

* [Official University of Pennsylvania Ph.D. Dissertation LaTeX Template (Overleaf)](https://www.overleaf.com/latex/templates/university-of-pennsylvania-ph-dot-d-dissertation-latex-template/gwtjmqdbfxgm)
* [Resources for Graduating PhD Students](https://provost.upenn.edu/for-students/graduate-and-professional-education/graduate-degrees/phd-students/)
  * [Dissertation Formatting](https://provost.upenn.edu/for-students/graduate-and-professional-education/graduate-degrees/phd-students/dissertation-formatting/)
    * [Formatting Guide](https://provost.upenn.edu/wp-content/uploads/Penn-Dissertation-Formatting-Guide-15.docx)
    * [Formatting Checklist](https://provost.upenn.edu/wp-content/uploads/PhD-Candidate-Formatting-Checklist_0.pdf)
  * [Sample Dissertation Title Page](https://provost.upenn.edu/for-students/graduate-and-professional-education/graduate-degrees/phd-students/sample-dissertation-title-page/)
  * [Graduate Groups](https://provost.upenn.edu/for-students/graduate-and-professional-education/graduate-degrees/graduate-group-coordinators/graduate-groups/)
  * [Copyright](https://provost.upenn.edu/for-students/graduate-and-professional-education/graduate-degrees/phd-students/dissertation-copyright/)
