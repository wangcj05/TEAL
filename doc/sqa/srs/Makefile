LATEX_FLAGS=-interaction=nonstopmode

all: TEAL_software_requirements_specifications.pdf

TEAL_software_requirements_specifications.pdf : TEAL_software_requirements_specifications.tex TEAL_software_requirements_specifications.bib intro.tex ../../version.tex ../sdd/TEALDepAndLimitations.tex
	python readRequirementsAndCreateLatex.py -i requirements_list.xml -o requirements.tex 
	pdflatex $(LATEX_FLAGS) TEAL_software_requirements_specifications.tex
	pdflatex $(LATEX_FLAGS) TEAL_software_requirements_specifications.tex
	pdflatex $(LATEX_FLAGS) TEAL_software_requirements_specifications.tex

../../version.tex : *.tex
	git log -1 --format="%H %an %aD" .. > ../../version.tex

default: *.tex

.PHONY: clean

clean:
	@rm -f *~ *.aux *.bbl *.blg *.log *.out *.toc *.lot *.lof TEAL_software_requirements_specifications.pdf
