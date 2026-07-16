.PHONY: all bachelor-en bachelor-it master-en master-it demos clean

# Same toolchain used by the default Overleaf pdfLaTeX build.
define build
	pdflatex -interaction=nonstopmode -halt-on-error $(1).tex
	bibtex $(1)
	pdflatex -interaction=nonstopmode -halt-on-error $(1).tex
	pdflatex -interaction=nonstopmode -halt-on-error $(1).tex
endef

all:
	$(call build,main)

bachelor-en:
	$(call build,variant-bachelor-english)

bachelor-it:
	$(call build,variant-bachelor-italian)

master-en:
	$(call build,variant-master-english)

master-it:
	$(call build,variant-master-italian)

demos: bachelor-en bachelor-it master-en master-it

clean:
	rm -f *.aux *.bbl *.blg *.lof *.log *.lot *.out *.toc *.run.xml *.bcf *.fls *.fdb_latexmk *.synctex.gz *.pdf
