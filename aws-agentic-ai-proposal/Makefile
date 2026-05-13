# AWS Agentic AI Spring 2026 Proposal Build System
# Usage:
#   make          — build proposal PDF
#   make budget   — build budget PDF
#   make all-pdfs — build both
#   make watch    — continuous rebuild on changes (proposal)
#   make clean    — remove build artifacts
#   make open     — build and open proposal PDF
#   make publish  — build and copy both PDFs to docs/

MAIN = main
BUDGET = budget
PDF = $(MAIN).pdf
BUDGET_PDF = $(BUDGET).pdf

.PHONY: all all-pdfs budget watch clean open publish

all: $(PDF)

all-pdfs: $(PDF) $(BUDGET_PDF)

$(PDF): $(MAIN).tex references.bib
	pdflatex -interaction=nonstopmode $(MAIN).tex
	bibtex $(MAIN)
	pdflatex -interaction=nonstopmode $(MAIN).tex
	pdflatex -interaction=nonstopmode $(MAIN).tex

budget: $(BUDGET_PDF)

$(BUDGET_PDF): $(BUDGET).tex
	pdflatex -interaction=nonstopmode $(BUDGET).tex

watch:
	latexmk -pdf -pvc -interaction=nonstopmode $(MAIN).tex

clean:
	rm -f *.aux *.bbl *.blg *.fdb_latexmk *.fls *.log *.out *.synctex.gz *.toc *.nav *.snm *.vrb *.run.xml *-blx.bib *.bcf

open: $(PDF)
	open $(PDF)

publish: $(PDF) $(BUDGET_PDF)
	cp $(PDF) ../docs/aws-agentic-ai-proposal.pdf
	cp $(BUDGET_PDF) ../docs/aws-agentic-ai-proposal-budget.pdf
	@echo "Published to docs/aws-agentic-ai-proposal.pdf and docs/aws-agentic-ai-proposal-budget.pdf"
