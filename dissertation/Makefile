all: dissertation.pdf

introduction/introduction.tex: introduction/introduction.rnw
	cd introduction && Rscript -e "library(knitr); knit('introduction.rnw')"

background/background.tex: background/background.rnw
	cd background && Rscript -e "library(knitr); knit('background.rnw')"

detection/detection.tex: detection/detection.rnw
	cd detection && Rscript -e "library(knitr); knit('detection.rnw')"

methods/methods.tex: methods/methods.rnw
	cd methods && Rscript -e "library(knitr); knit('methods.rnw')"

pf/pf.tex: pf/pf.rnw
	cd pf && Rscript -e "library(knitr); knit('pf.rnw')"

chimp/chimp.tex: chimp/chimp.rnw
	cd chimp && Rscript -e "library(knitr); knit('chimp.rnw')"

discussion/discussion.tex: discussion/discussion.rnw
	cd discussion && Rscript -e "library(knitr); knit('discussion.rnw')"

full/dissertation.tex: introduction/introduction.tex background/background.tex detection/detection.tex methods/methods.tex pf/pf.tex chimp/chimp.tex discussion/discussion.tex full/dissertation.rnw
	cd full && Rscript -e "library(knitr); knit('dissertation.rnw')"

dissertation.pdf: full/dissertation.tex full/tufte-book.cls full/tufte-common.def
	cd full && pdflatex dissertation.tex && bibtex dissertation.aux && pdflatex dissertation.tex && pdflatex dissertation.tex
	#cd full && pdflatex dissertation.tex && pdflatex dissertation.tex && pdflatex dissertation.tex
	cp full/dissertation.pdf dissertation.pdf

tidy:
	rm -f full/dissertation.pdf full/dissertation.tex full/dissertation.aux full/dissertation.idx full/dissertation.lof full/dissertation.log full/dissertation.lot full/dissertation.out full/dissertation.toc full/texput.log full/dissertation.bbl full/dissertation.blg full/dissertation.fdb_latexmk full/dissertation.fls full/dissertation.ilg full/dissertation.ind introduction/introduction.tex background/background.tex detection/detection.tex methods/methods.tex pf/pf.tex chimp/chimp.tex discussion/discussion.tex

clean: tidy
	rm -f dissertation.pdf
