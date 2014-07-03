all: dissertation.pdf

recombination.tex: 
	cd recombination && Rscript -e "library(knitr); knit('recombination.rnw')"

full/dissertation.tex: recombination/recombination.tex
	cd full && Rscript -e "library(knitr); knit('dissertation.rnw')"

dissertation.pdf: full/dissertation.tex
	#cd full && pdflatex dissertation.tex && bibtex dissertation.aux && pdflatex dissertation.tex && pdflatex dissertation.tex
	cd full && pdflatex dissertation.tex && pdflatex dissertation.tex && pdflatex dissertation.tex
	cp full/dissertation.pdf dissertation.pdf

tidy:
	rm -f full/dissertation.pdf full/dissertation.tex full/dissertation.aux full/dissertation.idx full/dissertation.lof full/dissertation.log full/dissertation.lot full/dissertation.out full/dissertation.toc full/texput.log full/dissertation.bbl full/dissertation.blg full/dissertation.fdb_latexmk full/dissertation.fls full/dissertation.ilg full/dissertation.ind recombination/recombination.tex

clean: tidy
	rm -f dissertation.pdf
