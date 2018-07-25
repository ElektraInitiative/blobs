#!/usr/bin/make -f

GS := /usr/bin/gs

## Create a PDF 1.3 out of inkscape PDF
# Additional Resources:
# * https://www.ghostscript.com/doc/current/Ps2pdf.htm#PDFX
# * http://zeroset.mnim.org/2014/07/14/save-a-pdf-to-cmyk-with-inkscape/

PROFILE := profile/PSOcoated_v3.icc

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
		-sOutputICCProfile=${PROFILE} \
		-dPDFX \
		-sOutputFile=$@ \
		tmp.pdf
