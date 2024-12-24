# -------------------------------
# Pandoc Settings
# -------------------------------

# The flags are explained at https://pandoc.org/MANUAL.html
# The options after "--pdf-engine-opt" are for latexmk, documented
# at https://github.com/debian-tex/latexmk#readme.

# Options for all output formats
PANDOC_OPTIONS = --listings \
		--number-sections \
		--pdf-engine=latexmk \
		--pdf-engine-opt=-bibtex \
		--pdf-engine-opt=-pdfxe \
		--pdf-engine-opt=-emulate-aux-dir \
		--pdf-engine-opt=-aux-directory=aux \
		--biblatex \
		--include-in-header templates/head_a.tex \
		--include-in-header info/info.tex  \
		--include-in-header templates/head_b.tex \
		--include-in-header templates/head_c.tex \
		--metadata-file=templates/info.md

main.pdf : main.md
	pandoc $< $(PANDOC_OPTIONS) -o $@

# Installing entr ( https://github.com/eradman/entr )
# will allow you to automatically compile your document
# every time you save the file main.md.
watch :
	find main.md  | entr -p -c 'make'

clean:
	rm -f main.pdf
	rm -rf aux
	rm -rf ../tex_version/

tex: main.md
	@pandoc $(PANDOC_OPTIONS) -s $< -o main.tex
	@mkdir -p ../tex_version/
	@cp -r main.tex fonts/ references/ pictures/ pdf/ code/ ../tex_version/
	sed -i '1i % !TeX program = xelatex\n% !BIB program = biber\n\n%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%\n% Welcome! Do not anything until "%%% To be filled %" %\n%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%\n' ../tex_version/main.tex	
	@echo "Your .tex version is available at ../tex_version/. Compile with latexmk -pdf -xelatex main.tex"

# This recipe checks that the md and tex version produce identical pdfs.
check: | tex main.pdf
	@cd ../tex_version/
	@latexmk -pdf -silent -xelatex main.tex
	@cmp --silent main.pdf ../md_version/main.pdf && echo '### SUCCESS: Files Are Identical! ###' || echo '### WARNING: Files Are Different! ###'
