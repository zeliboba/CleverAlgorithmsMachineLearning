# Makefile for the book

PAPERBACK=master

# Build the PDF for the paperback
paperback : ${PAPERBACK}.tex
	pdflatex ${PAPERBACK};true
	./make_bibtex.sh;true	
	pdflatex ${PAPERBACK};true
	pdflatex ${PAPERBACK};true
	makeindex ${PAPERBACK};true
	pdflatex ${PAPERBACK};true
	pdflatex ${PAPERBACK};true
	grep -i "undefined" ${PAPERBACK}.log;true

# Build the PDF for lulu
lulu : ${PAPERBACK}.tex
	pdflatex ${PAPERBACK};true
	./make_bibtex.sh;true	
	pdflatex ${PAPERBACK};true
	pdflatex ${PAPERBACK};true
	makeindex ${PAPERBACK};true
	pdflatex ${PAPERBACK};true
	pdflatex ${PAPERBACK};true
	grep -i "undefined" ${PAPERBACK}.log;true
	ps2pdf13 -dPDFSETTINGS=/prepress ${PAPERBACK}.pdf ${PAPERBACK}-lulu.pdf

# Delete all the guff and build matter
clean : 
	rm *.pdf *.out *.bbl *.blg *.aux *.idx *.log *.toc *.ilg *.ind

# View the PDF on Linux
vl:
	acroread ${PAPERBACK}.pdf

# View the PDF on Mac
vm:
	open -a Preview ${PAPERBACK}.pdf
