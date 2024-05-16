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
they were not before.  The total number of rows that had NaN's initially is very large, so the dataset is essentially unuseful without fixing the NaN issue, so we must be 
brave and assume the best regarding the updated data with no NaN's.  We may have skewed the data a bit by setting NaNa's to 'never' - perhaps we should have picked randomly from
a distribution of existing values?  But for the sake of time we are moving forward with the 'never' solution, as a series of "value_counts()" seems to imply that the damage will
be statistically small from this simplification.

We then started working threw the assigned analysis.  The value_counts(normalized = True) method is particulaly useful for determining the acceptance rate (the "Y" column) for any given subset of the population.  I believe the subsets considered are not really an exhaustive set, so there are possible sets we didn't consider that have even higher acceptance rates.  However, the considered subsets give a useful intuition about who is likely to accept bar coupons at a higher rate.  

The bar chart in question 5 was initially problematic as it became largely grayed out, but the high number of data points that were considered and the bar chart attribute that each data point is displayed by a small gray retangle, with the effect that the entire graph is largely grayed out in the obvious version of this graph.  We therefore created a "tidy" plot by creating a temporary dateset with sums for each type of coupon accepted, and that made the bar plot much more estetically pleasing. 




