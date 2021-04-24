# Government-Modeling (first past the post)

The code below is used to model first-past-the-post (= plurality) voting systems (for now; I may add other systems later). I was interested how many votes are typically 'dropped' in such a voting system.

The code can then be used to run a number of elections (e.g. 100,000) and see the average number of votes dropped overall.

Assumptions:

the votes per party are drawn at random from a gaussian distribution of 1,000 numbers (rounded to nearest 4 decimals). Gaussianity is a reasonable assumption (see e.g. https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3478593/)

alternatively (if there's no mean and standard deviation) votes per party are drawn simply by random choice of integers from 0-100. This assumption is extremely naive and not recommended

Inputs:

a list of the number of constituents per MP (can be generic, e.g. 10,000 constituents per MP, or even more specific if data on constituents per MP are available)

number of parties: int

number of elections: int

mean: float (mean of percentage of votes cast for all parties), default=None

stdev: float (standard deviation of votes cast for all parties), default=None

party parameters: list of tuples where each tuple's first element is the mean votes of the respective party (float) and the second element is that same party's standard deviation (float), default=None

verbose: Boolean

Outputs:

percentage of votes dropped

number of votes dropped

if verbose==True, further outputs are: an np.array with percentages of votes, dictionary of constituents per party
