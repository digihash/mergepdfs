# mergepdfs

Simple command line tool for merging and printing pdfs for duplex printing as a single job.

Note that I am aware of the fact that the code could be cleaner. It just works ☺.
The code for generating a blank PDF is based on [a post by Dingo on stackoverflow](http://stackoverflow.com/questions/9820830/how-to-merge-pdf-filesor-ps-if-not-possible-such-that-every-file-will-begin-in/9827598#9827598).

## Dependencies
Ruby 1.8.7 or newer, `pdftk`. Installing `pdfinfo` speeds up the merging process.

This program should run on all UNIX systems. Tested on Ubuntu 12.04, Ubuntu 13.04 and OS X Mountain Lion.

## Installation
In order to use this tool, simply put the files on your path.

	sudo su
	cd /opt
	git clone https://github.com/jmerlevede/mergepdfs.git
	ln -s /opt/mergepdfs/mergepdfs /usr/local/bin/mergepdfs
	ln -s /opt/mergepdfs/printpdfs /usr/local/bin/printpdfs


## mergepdfs
`mergepdfs --help`

	mergepdfs 1.0 by Jonathan Merlevede
	Usage:	mergepdfs output[.pdf]
		mergepdfs input1[.pdf] input2[.pdf] ... output[.pdf]

	mergepdfs is a simple command line script for merging PDF 
	files. White pages are added so that each of the PDF files 
	that is merged starts on an uneven page. The resulting 
	output file can then be printed as a single file in duplex 
	mode. 

	When not specifying input files, the script processes all 
	PDFs in the active directory. 

	Dependencies: pdftk

## printpdfs
`printpdfs --help`

	printpdfs 1.0 by Jonathan Merlevede
	Usage:	printpdfs -p printer input1[.pdf] input2[.pdf] ... 
		printpdfs input1[.pdf] input2[.pdf] ... 
		printpdfs

	printpdfs is a simple command line script for printing PDF 
	files in duplex mode as a single print job, with each PDF 
	file starting on a new sheet of paper. 

	Use the -p option to specify the name of a printer to send 
	the print job to. It is not necessary to type out the name 
	of the printer in full. 

	When not specifying input files, the script processes all 
	PDFs in the active directory. 

	Dependencies: mergepdfs, lpstat, lp
