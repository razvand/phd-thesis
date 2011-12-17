# image conversions (.dia to .eps, .eps to .pdf)

DIA = dia
INKSCAPE = inkscape
EPSTOPDF = epstopdf

DIA_FILES = monalisa-monitoring.dia log-parsing-workflow.dia \
	    ppf-architecture.dia
EPS_FILES = $(DIA_FILES:.dia=.eps) $(SVG_FILES:.svg=.eps)
PDF_FILES = $(DIA_FILES:.dia=.pdf) $(SVG_FILES:.svg=.pdf)
PNG_FILES = $(DIA_FILES:.dia=.png) $(SVG_FILES:.svg=.png)

all: $(PDF_FILES) $(PNG_FILES)

%.pdf: %.eps
	$(EPSTOPDF) $<

%.eps: %.dia
	$(DIA) -t eps-pango -e $@ $<

%.png: %.dia
	$(DIA) -t png -e $@ $<

%.eps: %.svg
	$(INKSCAPE) -E $@ $<
