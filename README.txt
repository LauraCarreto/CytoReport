# FUNCTION: Upload, check and process cytogenetics Sample Report files to produce a 
#	tab separated values (tsv) file in a user defined format (see example file Template.xls).
#
# ARGUMENTS: Cytogenetics Sample Report file (xml format) and the respective 
# 	Interval Based Report (IBR) file (xls extension; tab delimited format)
#
# RETURNS: Uploads the input Sample Report (xml) and IBR (xls) files.
# 	Produces an excel workbook as temporary file in folder /tmp/
#	Converts excel workbook into tab separated values file (txt) in a defined folder
#	Deletes uploaded Sample Report (xml) and IBR (xls) files.
#	Returns html file to browser with acknowledgement of processing and prompts
#	the user to restart with different files.
#
# NOTES: The web page cytoReport.html is used to upload the two input files and direct
#	filenames as arguments to the perl CGI script (cytoReport_tsv.pl).
#	Secure mode -T in cytoReport_tsv.pl was disabled so that system commands could be passed to convert 
# 	the excel workbook to csv (ssconvert), change comma separators to tab separators,
#	and line separators from linefeed to "|" (vertical tab symbol), to output the tsv file.
#     The input files and the csv file are deleted after processing.
