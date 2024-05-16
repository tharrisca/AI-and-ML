# Assignment 5.1: Professional Certification on AI and ML
## Student: Tim Harris
## May 16th, 2024
##
Initiallization:  We noticed that print statements were only working once per cell, which was slowing down diagnostics.  We set:
`from IPython.core.interactiveshell import InteractiveShell
InteractiveShell.ast_node_interactivity = "all" `

This succeeding in fixing the observed I/O issue with cells.

## Problems
For brevity we outline only highlights of problem solving that are not obvious from the actual notebook.  

The input data coupons.csv is highly normalized with many columns.  Many NaN's exist (not a number) and the cars column is not complete enough to have value.
Therefore the cars column will be ignored in this analysis.  There are naming issues as some columns start with capitalized letters, and some with lower case letters.
We ignore this issue.  There is one column which is misspelled - the passenger column is spelled "passanger".  This could cause problems for later consumers of the data
so we rename this column to "passenger".  We reset all NaN to "never", with hopes it doesn't change the data distribution much but makes many rows useful in a way 
they were not before.  The total number of rows that had NaN's initially is very large, so the dataset is essentially unuseful without fixing the NaN issue.  
