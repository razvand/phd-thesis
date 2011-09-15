# image conversions (.dia to .eps, .eps to .pdf)

DIA = dia
INKSCAPE = inkscape
EPSTOPDF = epstopdf

DIA_FILES = architecture-overview.dia detailed-architecture.dia \
	    multiparty-sendmsg.dia multiparty-recvmsg.dia \
	    multiparty-net-header.dia multiparty-net-header2.dia
EPS_FILES = $(DIA_FILES:.dia=.eps) $(SVG_FILES:.svg=.eps)
PDF_FILES = $(DIA_FILES:.dia=.pdf) $(SVG_FILES:.svg=.pdf)

all: $(PDF_FILES)

%.pdf: %.eps
	$(EPSTOPDF) $<

%.eps: %.dia
	$(DIA) -t eps-pango -e $@ $<

%.eps: %.svg
	$(INKSCAPE) -E $@ $<