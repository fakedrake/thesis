all: show

show: presentation.pdf
	open presentation.pdf

DIAGRAM_SOURCES=$(shell find diagrams -name "*.dot" -print)
DIAGRAMS=$(DIAGRAM_SOURCES:%.dot=%.png)
clean:
	rm -rf $(DIAGRAMS) presentation.pdf

%.ps: %.dot
	dot -Tps -x $< -o $@

%.png: %.dot
	dot -Tpng $< -o $@

presentation.pdf: presentation.tex $(DIAGRAMS)
	xelatex -interaction nonstopmode $< || true
