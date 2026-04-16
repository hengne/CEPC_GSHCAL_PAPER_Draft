# Makefile for GS-HCAL paper — builds NIM A, JHEP, and NST versions
# Usage:
#   make          — build all three versions
#   make nima     — build only NIM A
#   make jhep     — build only JHEP
#   make nst      — build only NST
#   make clean    — remove all build artifacts

LATEXMK = latexmk
LATEXMKFLAGS = -pdf -interaction=nonstopmode -halt-on-error

.PHONY: all nima jhep nst clean

all: main_nima.pdf main_jhep.pdf main_nst.pdf

nima: main_nima.pdf
jhep: main_jhep.pdf
nst:  main_nst.pdf

main_nima.pdf: main_nima.tex body.tex gshcal.bib $(wildcard figs/*)
	$(LATEXMK) $(LATEXMKFLAGS) $<

main_jhep.pdf: main_jhep.tex body.tex gshcal.bib jheppub.sty JHEP.bst $(wildcard figs/*)
	$(LATEXMK) $(LATEXMKFLAGS) $<

main_nst.pdf: main_nst.tex body.tex gshcal.bib $(wildcard figs/*)
	$(LATEXMK) $(LATEXMKFLAGS) $<

clean:
	rm -f *.aux *.bbl *.blg *.log *.out *.spl *.fdb_latexmk *.fls *.synctex.gz
	rm -f main_nima.pdf main_jhep.pdf main_nst.pdf
