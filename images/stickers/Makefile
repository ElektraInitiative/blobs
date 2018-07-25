#!/usr/bin/make -f

GS := /usr/bin/gs

## Create a PDF 1.3 out of inkscape PDF

%.pdf: %.svg
	# Export SVG
	inkscape $< --export-pdf=tmp.pdf
	# Run ghostscript
	${GS} \
		-dSAFER \
		-dBATCH \
		-dNOPAUSE \
		-dNOCACHE \
		-sDEVICE=pdfwrite \
		-sColorConversionStrategy=CMYK \
		-dProcessColorModel=/DeviceCMYK \
		-dPDFX \
		-sOutputFile=$@ \
		tmp.pdf
