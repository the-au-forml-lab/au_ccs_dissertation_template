# Augusta University School of Computer and Cyber Sciences Ms and PhD Template

## Presentation

This template was designed for Ms and PhD students from the [School of Cyber and Computer Sciences](https://www.augusta.edu/ccs/) at [Augusta University](https://www.augusta.edu/) as an alternative to the standard, ["ETD"](https://guides.augusta.edu/ld.php?content_id=64866487) template offered by the Graduate School.
Students more comfortable with the `docx` format or not willing to learn to use [LaTeX](https://www.latex-project.org/) and / or [markdown](https://commonmark.org/) should use this standard template instead.

> [!CAUTION]
> The student and their advisor are strongly encouraged to make sure that the manuscript comply with the [Forms, Policies, and Procedures](https://www.augusta.edu/gradschool/student-resources.php) of [Augusta University](https://www.augusta.edu/)'s [Graduate School](https://www.augusta.edu/gradschool/) themselves.
> This template was developed with 


This template is offered in two versions:

- The [`tex` version](tex_version) is a standard `tex` document that can be compiled using [latexmk](https://mg.readthedocs.io/latexmk.html) or any standard LaTeX distribution,
- The [markdown version](md_version) is a [markdown](https://commonmark.org/) document that can be compiled using [pandoc](https://pandoc.org/).

Note that the `tex` version is actually obtained from the markdown version, thanks to pandoc's ability to convert markdown documents into `tex` documents.
This conversion takes place when the markdown version is used to produce the final `pdf` "under the hood", which allows the markdown version to use _both_ the LaTeX and the markdown syntaxes.
Both versions are commented and links to relevant documentations / questions are included.

Important notice:
    Those documents have been approved by the graduate school and the University Libraries regarding the font, spacing, margins, and other important conventions. Please, do not edit portions of the documents labeled 
    
    ⚠ Do not edit ⚠ 

### Details on the `tex` version

The `tex` version of this template can be compiled using [latexmk](https://mg.readthedocs.io/latexmk.html), by running 

    latexmk -pdf -xelatex main.tex

in the tex_version folder. The "main.tex" document is "standalone" in the sense that it is not divided into smaller `tex` files, but students should feel free to split it by using the [`\input{…}` and `\include{…}` commands](https://tex.stackexchange.com/q/246/34551).


Start by looking for

    %%%%%%%%%%%%%%%%%%
    %%% To be filled %
    %%%%%%%%%%%%%%%%%%
    
and replace the values of the commands from `\yourtitle{…}` to `\yourdate{…}`, uncommenting `\togglefalse{ms}` and commenting `\toggletrue{ms}` if you are a PhD student.


#### Requirements

- [LaTeX](https://www.latex-project.org/get/),
- [latexmk](https://mg.readthedocs.io/latexmk.html) (it is possible that it is already part of your LaTeX installation).

### Details on the markdown version

The markdown version of this template can be compiled using [pandoc](https://pandoc.org/), by running

    make
    
in the md_version folder. 

Start by editing the file info/info.tex with your information.

#### Requirements

- The ability to execute [makefile](https://en.wikipedia.org/wiki/Makefile) (e.g., a UNIX system, a system with [Cygwin](https://en.wikipedia.org/wiki/Cygwin), or [some other trick](https://stackoverflow.com/q/2532234/)), or you can also simply open the [makefile](md_version/makefile) file to "extract" the pandoc options needed to compile properly this document,
- the latest version of [pandoc](https://pandoc.org/installing.html),
- [LaTeX](https://www.latex-project.org/get/) (refer to the instructions on the [pandoc installation page](https://pandoc.org/installing.html) or at  <https://tex.stackexchange.com/q/1092>), it is probaby better to install a minimal installation, and then to fetch the missing packages one by one, using e.g. `/usr/local/texlive/2021/bin/x86_64-linux/tlmgr install environ` for the `environ` package,
- [latexmk](https://mg.readthedocs.io/latexmk.html) ([version 4.74. or higher](https://github.com/aubertc/au_ccs_dissertation_template/issues/1), it is possible that it is already part of your LaTeX installation),
- [entr](https://github.com/eradman/entr) if you want  to use the command `make watch` that automatically re-compile your source when it is saved.


## Additional Information

Please, refer to the [Thesis/PhD Dissertation Preparation Booklet](https://www.augusta.edu/gradschool/documents/thesis-dissertation-preparation-booklet.pdf) from the graduate school and the University Libraries for additional information, tips and advises.


## Credits and Licence

- This template was created taking inspiration from Augusta University's [Biostat dissertation template](https://guides.augusta.edu/ld.php?content_id=78256224).
- This template uses and redistributes the [TeX Gyre Termes](http://www.gust.org.pl/projects/e-foundry/tex-gyre/termes) font (version 2.004), placed under the [GUST Font License](https://tug.org/fonts/licenses/GUST-FONT-LICENSE.txt), which is an extension of the [The LaTeX Project Public License](https://www.latex-project.org/lppl.txt).
- This template uses and redistributes the [Symbola](http://web.archive.org/web/20180307012615/http://users.teilar.gr/~g1951d/Symbola.zip) font (version 10.24), which is "free for any use".
- The file code/hello_world.c is courtesy of Brian Kernighan.
- The file pictures/D_un_autre_age.jpg is courtesy of [Jérôme Minard](http://jeromeminard.com/travaux/) and under [copyleft](https://forceg.jimdofree.com/licence-art-libre/).
- Unless otherwise noted, this template is under [Creative Commons Attribution 4.0 International](LICENSE.md).
- © [Our contributors](https://github.com/the-au-forml-lab/au_ccs_dissertation_template/graphs/contributors), 2021-2025
