# This Makefile was taken from https://github.com/aknierim/TikZ_assortment

TeXInputs = TEXINPUTS=..:

TIKZFILES := $(wildcard *.tex) # list of all TikZ files
TIKZ_PDFS := $(addprefix build/,$(subst ,,$(TIKZFILES:.tex=.pdf))) # get names from TikZ files for .pdf output files


all: $(TIKZ_PDFS)

$(TIKZ_PDFS): FORCE | build
	$(TeXInputs) latexmk -r ../latexmkrc $(TIKZFILES)

FORCE:

preview: FORCE | build
	$(TeXInputs) latexmk -r ../latexmkrc -pvc $(TIKZFILES)

build:
	mkdir -p build/

clean:
	rm -rf build

.PHONY: FORCE all clean move