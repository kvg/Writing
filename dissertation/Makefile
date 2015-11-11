all: dissertation.pdf

motivation/motivation.tex: motivation/motivation.rnw motivation/figure/*.pdf
	cd motivation && Rscript -e "library(knitr); knit('motivation.rnw')"

background/background.tex: background/background.rnw
	cd background && Rscript -e "library(knitr); knit('background.rnw')"

simulation/simulation.tex: simulation/simulation.rnw simulation/figure/*.pdf
	cd simulation && Rscript -e "library(knitr); knit('simulation.rnw')"

detection/detection.tex: detection/detection.rnw detection/figure/*.pdf
	cd detection && Rscript -e "library(knitr); knit('detection.rnw')"

pf/pf.tex: pf/pf.rnw
	cd pf && Rscript -e "library(knitr); knit('pf.rnw')"

chimp/chimp.tex: chimp/chimp.rnw
	cd chimp && Rscript -e "library(knitr); knit('chimp.rnw')"

discussion/discussion.tex: discussion/discussion.rnw
	cd discussion && Rscript -e "library(knitr); knit('discussion.rnw')"

full/dissertation.tex: full/acknowledgements.tex full/dedication.tex full/abstract.tex motivation/motivation.tex background/background.tex simulation/simulation.tex detection/detection.tex pf/pf.tex chimp/chimp.tex discussion/discussion.tex full/dissertation.rnw /Users/kiran/Documents/allpapers.bib
	cd full && Rscript -e "library(knitr); knit('dissertation.rnw')"

dissertation.pdf: full/dissertation.tex full/tufte-book.cls full/tufte-common.def
	cd full && pdflatex dissertation.tex
	cd full && bibtex dissertation.aux
	cd full && pdflatex dissertation.tex
	cd full && pdflatex dissertation.tex
	cp full/dissertation.pdf dissertation.pdf

tidy:
	rm -f full/dissertation.pdf full/dissertation.tex full/dissertation.aux full/dissertation.idx full/dissertation.lof full/dissertation.log full/dissertation.lot full/dissertation.out full/dissertation.toc full/texput.log full/dissertation.bbl full/dissertation.blg full/dissertation.fdb_latexmk full/dissertation.fls full/dissertation.ilg full/dissertation.ind motivation/motivation.tex background/background.tex simulation/simulation.tex detection/detection.tex pf/pf.tex chimp/chimp.tex discussion/discussion.tex

clean: tidy
	rm -f dissertation.pdf
