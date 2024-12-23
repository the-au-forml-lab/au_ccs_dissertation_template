<!--
This is the file that will contain your manuscript.
Indications are given below, and all the files
are commented in case you want to tweak them.
Make sure you do not alter one of the required 
aspect of the template, labeled with
⚠ Do not edit ⚠


█░█ ▄▀█ █▀█ █▀█ █▄█  
█▀█ █▀█ █▀▀ █▀▀ ░█░  

█░█░█ █▀█ █ █▀▀ █ █▄░█ █▀▀
▀▄▀▄▀ █▀▄ █ ░█░ █ █░▀█ █▄█

█▀▀ █▀█ █▀▄ █ █▄░█ █▀▀
█▄▄ █▄█ █▄▀ █ █░▀█ █▄█  

█░█ ▄▀█ █▀▀ █▄▀ █ █▄░█ █▀▀   █
█▀█ █▀█ █▄▄ █░█ █ █░▀█ █▄█   ▄
--> 

<!--
Enter your dedication here. It can not contain empty lines,
and must be written in LaTeX, so you can create new lines
using "\\" and "\\[2em]" if you want more space.
-->

\dedication{
This part serves two purposes.\\[1em]
To write the acknowledgments (as a \enquote{\emph{Thank you note}}).
You can look for inspiration~\cite{Chisholm} if you need some.\\[1em]
To include a detailed summary of the work performed by other authors on published or accepted manuscripts used in the thesis / dissertation, if applicable.
}

<!-- 
⚠ Do not edit ⚠
Having an abstract is mandatory, even if its content, 
of course, is up to you.

This abstract must be written in LaTeX.
Your name, the title of the manuscript and your advisor name
will be automatically inserted at the beginning.
The keywords will be automatically inserted at the end.
-->

\begin{abstract}
The abstract must not exceed 350 words.
It must consist of the briefest possible summary of the thesis / dissertation and the conclusions reached.
Explanatory matter and opinion must be omitted.
\end{abstract}

\cleardoublepage
\pagenumbering{arabic}

<!--
All the rest of the document can be written either in Latex,
or in markdown it is up to you. Some insights are given below,
but you should feel free to erase all of it.
-->

# Introduction

This document is a guide on how to use it ("how meta!"), and its structure does not reflect the structure of a Thesis: you will need to erase (almost) all of its body and fill it with your own, organized in a coherent manner respectful of your reader's expectations, of your fields guidelines, and in agreement with your advisor.
Note that The Graduate School recommends using APA [@American_Psychological_Association2023] and that using another style requires approval of its Dean prior to writing the thesis or dissertation.

It is very important that you comply with all of the graduate school's policies [@gradschool_policies].
This template was carefully crafted with highest standards in mind, and respects all of the graduate schools requirements.
You can find additional information on the ["The Graduate School Reference Center: ETD Templates & Preparation Booklet"](https://guides.augusta.edu/graduateschool/template) or, more generally, on [this template's repository](https://github.com/aubertc/au_ccs_dissertation_template).

Normally, what you can and cannot edit is clearly labeled in the source code, either at the beginning of the file, or with 

> ⚠ Do not edit ⚠

Markdown only
~ The comments applicable only to the markdown version of this document are indicated in such environments.

## Title Levels 

As indicated in the koma-script manual, the class `scrbook` that is used for this document has access to 6 levels of titles:

```
\chapter{Test}
\section{Test}
\subsection{Test}
\subsubsection{Test}
\paragraph{Test}
\subparagraph{Test}
```

Only Chapters, Sections and Subsections will appear in the table of contents, by design.

Markdown only
~ Note that pandoc's `#` corresponds to Chapter, and that increasing the number of `#` increases the level of heading.

### Subsection

This is a subsection.

#### Subsubsection

This is a subsubsection.

##### Paragraph

This is a paragraph.

###### Sub-Paragraph

This is a sub-paragraph.

## Debugging

If this template does not "work" as expected, feel free to [open an issue](https://github.com/aubertc/au_ccs_dissertation_template/issues) or reach out to <caubert@augusta.edu>, after having looked at `aux/input.log` as (probably) indicated by latexmk.

# References and Bibliography

Prepare your references using \LaTeX's bibliography system [\BibTeX](http://www.bibtex.org/Using/): this template uses by default [biblatex](https://pandoc.org/MANUAL.html#citations), but you can [alter this behaviour](https://pandoc.org/MANUAL.html#citation-rendering) to use [natbib](https://www.ctan.org/pkg/natbib) if you prefer.

The references are stored in the .bib file located at `references/references.bib`: it contains examples of various entries.
In computer science, a good source of bibliographical references is the [dblp computer science bibliography](https://dblp.org/). 
Make sure to include the [digital object identifier](http://dx.doi.org/) (DOI) whenever possible, and note that this identifier can [be used to obtain the corresponding .bib entry](https://www.doi2bib.org/).
Finally, you can "tidy" your .bib file using [bibtex-tidy](https://flamingtempura.github.io/bibtex-tidy/).

The list of references is automatically inserted in [the list of references](#chap:references), p.\ \pageref{chap:references}. 
Use \LaTeX's `\cite` command to insert references.

Links are only underlined _on screen_ (and not in print), and with colors that should be [colourblind safe](https://tex.stackexchange.com/a/526148).


Markdown only
~ 
    You can use various syntaxes to integrate references: on top of \LaTeX's `\cite` command, [pandoc's](https://pandoc.org/MANUAL.html#citation-syntax) `[@key]`, as well as [more complex commands](https://github.com/jgm/pandoc/issues/2335), such as `\citeauthor` or pandoc's prefix, locator, and suffix, such as in `[see @key1, pp. 33-35 and *passim*; @key2, chap. 1]`.
    
    You can insert [hyperlinks](https://pandoc.org/MANUAL.html#links-1) in different ways, including hyperlinks to this document^[You may note that the footnote number is itself a link.] using e.g.\ the [link automatically added to all chapters](#introduction), following the convention described [in pandoc's manual](https://pandoc.org/MANUAL.html#heading-identifiers).


# Writing Mathematics{#writing-mathematics}

\LaTeX can be used to render [complex mathematics expressions](https://en.m.wikibooks.org/wiki/LaTeX/Mathematics) in a relatively simple manner.
Note that thanks to XeLaTeX, you can insert mathematical symbols directly [in unicode](https://en.wikipedia.org/wiki/Mathematical_operators_and_symbols_in_Unicode), as follows: $∀ y ∈ ℕ, ∃ x ∈ ℕ, y = x²$, but of course you can always fall back to usual \LaTeX{} notation, using e.g. `\forall` to produce $\forall$.

You can add additional unicode symbols that may not be supported by this template or its font using the model 

```latex
\newunicodechar{<unicode symbol>}{\ensuremath{<latex command>}}
```

(in `head_c.tex` in the markdown version), in this case additionally forcing the symbol `<unicode symbol>` to be rendered in math mode using `\ensuremath`.


## Theorem, Proof, and Others Environments

Markdown only
~ 
    You can state e.g.\ theorems and proofs using pandoc's built-in ["_Definition list_"](https://pandoc.org/MANUAL.html#definition-lists), that are rendered as `description` environments in \LaTeX.

    Theorem
    ~ 
        Every $n ∈ ℕ$, $n >1$ has a unique prime factorization.

    Proof
    ~ 
        Carl Friedrich Gauss told me so. \qed

To insert numbered theorems, definitions, and the like, and be able to reference them or add automatically the "qed" (□) symbol, you need to use \LaTeX's `theorem` environment, `label` commands, etc.
Note that, by default, proofs are unnumbered environments, but that there are [ways to reference them](https://tex.stackexchange.com/q/223352) if you want to.

\begin{theorem}[Pythagoras theorem]
\label{thm:pythagoras}
    \(∀ a, b, c, a²+b²=c²\).
\end{theorem}

\begin{proof}
    Proving \autoref{thm:pythagoras} is not that easy.
\end{proof}


Markdown only
~  If you would rather keep the "pure" markdown syntax but improve pandoc using a filter, you can look at [the pandoc filter "statement"](https://github.com/jdutant/statement) and its [discussion on related filters](https://github.com/jdutant/statement#related-filters), but it may be more difficult to install and use properly.

## Formal Proofs

You can easily represent formal proofs using \LaTeX's ebproof or bussproof packages:

\begin{center}
    \begin{prooftree}
        \hypo{A \vee B}
        \hypo{[A]}
        \ellipsis{}{C }
        \hypo{[B] }
        \ellipsis{}{C }
        \infer3[$\vee\textrm{E}$]{C}
    \end{prooftree}
\end{center}

# Inserting PDFs, Figures, Tables and (Code) Listings

## Inserting PDFs

PDF documents can be inserted using `pdfpages`'s `\includepdf` command.
For commodity, a `\modifiedincludepdf` is provided:

```tex
\modifiedincludepdf{options for includepdf}%
    {label}%
    {full path to the document}%
    {title of the document}%
    {"level" (e.g., section, subsection, etc.)}
```

Note that using `label.x` will refer to the page `x` of the inserted document (starting with 1): refer to the source code of this current document for an example usage.
We insert [in the following pages](#pdf:Gluck13) (pp. \pageref{pdf:Gluck13.1}--\pageref{pdf:Gluck13.9}) an article as an example of PDF insertion.

\modifiedincludepdf{}{pdf:Gluck13}{pdf/simulation_of_two_ways_pushdown_automata_revisited.pdf}{A paper proving concisely a result in automata theory that helped solve a real programming problem~\cite{DBLP:journals/corr/Gluck13}}{subsection}

## Inserting Figures

Markdown only
~  You can easily insert [images and figures](https://pandoc.org/MANUAL.html#images) using Pandoc, as in \autoref{fig:d_un_autre_age}, a painting by [Jérôme Minard](http://jeromeminard.com/travaux/) under [copyleft](https://forceg.jimdofree.com/licence-art-libre/).

![_D'un autre âge_\label{fig:d_un_autre_age}](pictures/D_un_autre_age.jpg){width=80%}


## Inserting Tables

Markdown only
~  You can write tables using [pandoc's syntax*es*](https://pandoc.org/MANUAL.html#tables), as in Tables \ref{tbl:demo1}, \ref{tbl:demo2} and \ref{tbl:demo3} (all borrowed from <https://www.flutterbys.com.au/stats/tut/tut17.3.html>).


  --------------------------------
  Column A    Column B      Column 
                                 C
  ---------  ----------  ---------
  Category 1    High        100.00
  High         95.00
  
  Category 2    High         80.50
  High         82.50
  --------------------------------

  : The price of categories \label{tbl:demo1}
  
  | Default | Left  | Center | Right  |
  |---------|:------|:------:|-------:|
  |   High  | Cat 1 | A      | 100.00 |
  |   High  | Cat 2 | B      |  85.50 |
  |   Low   | Cat 3 | C      |  80.00 |
  
  : Illustrating how to align entries in a table \label{tbl:demo2}

+---------------+---------------+--------------------+
| Fruit         | Price         | Advantages         |
+===============+===============+====================+
| Bananas       | $1.34         | - built-in wrapper |
|               |               | - bright color     |
+---------------+---------------+--------------------+
| Oranges       | $2.10         | - cures scurvy     |
|               |               | - tasty            |
+---------------+---------------+--------------------+
: The price and advantages of fruits \label{tbl:demo3}

## Inserting Code Listings

Code is displayed using the listings package.
Check the "Table 1: Predefined  languages" of the listings package documentation to see the list of supported languages by default.

Markdown only
~  Your can display code using [various possible syntaxes](https://pandoc.org/MANUAL.html#verbatim-code-blocks).

As a fenced block:

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World");
    }
}
```

In a figure, as in Listings \ref{lst:demo1}, \ref{lst:demo2} or \ref{lst:demo3} (that uses respectively the backtick, the tildes, and `listinputlisting` to display the code -- this latter option allows to load a file directly).

```{language=coq caption="An inductive definition in Coq" label="lst:demo1"}
(** Courtesy of https://coq.inria.fr/a-short-introduction-to-coq. **)
Inductive even : N -> Prop :=
| even_0 : even 0
| even_S n : odd n -> even (n + 1)
with odd : N -> Prop :=
| odd_S n : even n -> odd (n + 1).
```

~~~{.bash caption="How to use braces ({and }) in bash" label="lst:demo2"}
# Courtesy of https://stackoverflow.com/a/2188369
for num in {000..2}; do echo "$num"; done
~~~

\lstinputlisting[language=C, caption={"\emph{Hello World}" in C}, label={lst:demo3}]{code/hello_world.c}


# Landscape Pages

You can obtain landscape pages using the landscape package in \LaTeX.

Markdown only
~  This feature is not accessible in pure markdown: if you want to have landscape pages, you need to use \LaTeX commands in your document.

Note that the drawing presented in \autoref{fig:language} was obtained using \LaTeX's package tiKz, and that the source code is shared in the pictures folder.

\begin{landscape}
    \vspace*{\fill} 
    \begin{figure}
        \centering
        \includegraphics[width=\textheight]{pictures/languages_overview.pdf}
        \caption{Difference between programming languages (simplified)}
        \label{fig:language}
    \end{figure}
    \vspace*{\fill}
\end{landscape}

# Margins and Fonts

## Margins

The margin have been set to fit the graduate school's requirements to:

---

\printinunitsof{in}{\pagevalues}

---

Please, do not change those values.

## Fonts

### Body

The font used in the body of the document is ["TeX Gyre Termes Font Family"](http://www.gust.org.pl/projects/e-foundry/tex-gyre/termes), which is an extension of the standard Times New Roman that is free for commercial use, and can be [freely distributed](https://www.gust.org.pl/fonts/licenses/GUST-FONT-LICENSE.txt).
It is set to 12pt in all of the document, and adjusted when needed to the appropriate size (particularly in the cover page, where most attributes need to be set at 16pts).

The "usual" correspondence between points and \LaTeX commands is as follows:

\getfontsize

### Symbols

For better unicode support, the Symbola font is also used.
Starting [with version 11](http://web.archive.org/web/20181228102842/http://users.teilar.gr/%7Eg1951d/Symbola.pdf), the licence of this font is too restrictive for non-personal use.
As a consequence, users are asked to make sure they do not use a version greater than v.10.24, which is "free for any use" and [archived on-line](http://web.archive.org/web/20180307012615/http://users.teilar.gr/~g1951d/Symbola.zip).

By default, the following symbols, not available in the TeX Gyre Termes Font Family, are displayed using Symbola: 🔒, ✘, ⚠, ❓, 🔜, ℕ, ℤ, ✔, ↵, ↲, 🛡, ℝ □.
To declare other unicode symbols as having to be displayed using the Symbola font, use

```latex
\newunicodechar{<unicode symbol>}{\symb <unicode symbol>}
```

(in `head_c.tex` in the markdown version), so that `<unicode symbol>` will be rendered using the Symbola font.
 
<!--
⚠ Do not edit ⚠
the three lines below.
-->
\clearpage
\printbibliography[label=chap:references, title=References]
\let\printbibliography\relax
<!--
You can remove what follows if you do not need appendices.
-->

\appendix

# Appendix A (Optional)

Insert here protocols, figures not included, larger listings, etc.
