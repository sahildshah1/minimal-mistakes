---
published: true
title: "Are Vegas's NBA spreads accurate?"
---

## Introduction

When sports betting was [legalized](https://www.nytimes.com/2018/05/14/us/politics/supreme-court-sports-betting-new-jersey.html) this 
summer, it sparked a debate amongst my friends about whether Vegas is accurate
over the course of a season across the NBA  or if there's a bias that we
could theoretically exploit to `beat the house.'

In addition to taking bets on whether a team will win or lose straight up, Vegas
also a `spread' that handicaps the favored team. Vegas wants to set the point
spreads so that the chance of a team winning or losing is 50-50. This
incentivizes an equal number of bets on both sides of the bet and allows Vegas
to make money every time directly from commissions. Therefore if Vegas is
accurate, every team would win 50% of the time against the spread on average. 

With data on the on the win-loss records against the spread for the 2017-2018
NBA season, we can calculate how far each team was from 0.500 win record against
the spread and investigate the variation in this data.

Here's a dot plot of each team's record straight up and against the spread.

![](/assets/images/.png?raw=true){:.center-image}


## 


Here's a distribution of how far each team was from a 0.500 win record. 

![](/assets/images/.png?raw=true){:.center-image}


If Vegas were perfectly accurate, every team would have a 0.500 win record
(against the spread) and there wouldn't be any variation around 0 on the
histogram. Instead the average deviation from a 0.500 record (against the
spread) for the 2017-2018 NBA season was -0.013.

<!-- The teams with an above 0.500 win record (\ie positive values on the histogram) 
correspond to 
 -->

Based on this average, Vegas tended to set the lines slightly too high but 
we want to test whether this is statistically significant. 

Rather than make any assumptions about how the deviations from 0.500 are
distributed, we calculate an empirical bootstrap confidence interval. The 95
percent confidence interval  will correspond to a range of values that are
**not** rejected at a 0.05 significance level.

Therefore, if 0 fall within the 95 percent confidence interval we would conclude
that Vegas is on average accurate and if 0 falls outside of the 95 percent confidence
interval we would conclude that Vegas is on average inaccurate. 

To learn 
more about the relationship between confidence intervals and hypothesis testing
see [section 4](https://ocw.mit.edu/courses/mathematics/18-05-introduction-to-probability-and-statistics-spring-2014/readings/MIT18_05S14_Reading23a.pdf) of the linked class notes. 

After estimating the distribution of  how much the sample mean varies around
an underlying population mean (see [sections 6.3 and  6.4](https://ocw.mit.edu/courses/mathematics/18-05-introduction-to-probability-and-statistics-spring-2014/readings/MIT18_05S14_Reading24.pdf) of the linked class note to learn
more about the empirical bootstrap confidence interval and how and why it is 
calculated, we find that the 95 percent confidence interval is [-0.034, 0.006]

Since this range contains 0, we would conclude that Vegas is on average accurate 









## Introduction 



One question that came up was whether all the NBA teams were 0.500 against the spread.
In theory, lines should be set so that they *are* 0.500 against the spared and 
a site would make money off of their take. 


## Data and Exploratory Analysis 


![Dot Plot](/assets/images/0710ipynb-nba_spreads-dotplot.png?raw=true){: .center-image }

Boston over-performed relative to expectations and GSW under-performed relative
to expectations.  


## Discussion 

Cavs and Warriors underperformed. Do the lines get inflated because of the 
super-stars on the team? Do Lebron's team's over the past 5 year's have a similar
trend vs the spread? Do you get backdoor covers when they bench their starters?

If you bet the Warriors all year you would make money? Individual games?

## Methods

I scrubbed and visualized the data using Python and learned: 


- Visualized the data with seaborn

#### Split columns by delimiter 

- - str.split() can split Series by delimiter
- df[] indexes rows --> Selecting columns by position use the iloc function (https://pandas.pydata.org/pandas-docs/stable/10min.html)

- Python indexing is not inculsive?
(https://medium.com/dunder-data/selecting-subsets-of-data-in-pandas-6fcd0170be9c)

- str.split works on Series (i.e. each column of the data frame) so loop over columns and concat b/c split apply combine group by or apply function's didn't work and there's only 9 columns


#### Drop first row of "Team Total None None Home" and name columns 

NOTES

- Drop a row: scrubbed_dataframe.drop(scrubbed_dataframe.index[0])
- Rename columns https://erikrood.com/Python_References/rename_columns.html

- SUBSET data frame https://medium.com/dunder-data/selecting-subsets-of-data-in-pandas-6fcd0170be9c

    -  [] Primary purpose is to select columns by name
    - .loc select rows and columsn by name
    - .iloc select rows and coluumns by index 

- https://stackoverflow.com/questions/34844711/convert-entire-pandas-dataframe-to-integers-in-pandas-0-17-0/34844867


###  Vertical plot Descriptive analysis 

https://chrisalbon.com/python/data_wrangling/pandas_with_seaborn/

https://blog.modeanalytics.com/python-data-visualization-libraries/

Pandas allows you to select a single column as a Series by using dot notation. This is also referred to as attribute access. 

he biggest drawback is that you cannot select columns that have spaces or other characters that are not valid as Python identifiers (variable names).

Template code from : https://seaborn.pydata.org/examples/pairgrid_dotplot.html

https://stackoverflow.com/questions/33446029/how-to-change-a-figures-size-in-python-seaborn-package

.columns method 


https://medium.com/dunder-data/selecting-subsets-of-data-in-pandas-6fcd0170be9c
Earlier, we mentioned the three components of the DataFrame. The index, columns and data (values). We can extract each of these components into their own variables. Let’s do that and then inspect them:

https://stackoverflow.com/questions/28910851/python-pandas-changing-some-column-types-to-categories

https://stackoverflow.com/questions/14608483/how-to-add-a-grid-line-at-a-specific-location-in-matplotlib-plot

https://stackoverflow.com/questions/4918425/subtract-a-value-from-every-number-in-a-list-in-python

https://people.duke.edu/~ccc14/sta-663/ResamplingAndMonteCarloSimulations.html

NOTES:
​
- Matplotlib gallery : https://python-graph-gallery.com/category/matplotlib/
- seaborn gallery: https://seaborn.pydata.org/examples/index.html
​
- Using seaborn to visualize https://chrisalbon.com/python/data_wrangling/pandas_with_seaborn/

https://chrisalbon.com/python/data_wrangling/pandas_join_merge_dataframe/


Store a dataframe 

https://stackoverflow.com/questions/17098654/how-to-store-a-dataframe-using-pandas


### Debugging matplot lib 

https://stackoverflow.com/questions/47155569/difference-in-plotting-with-different-matplotlib-versions

https://stackoverflow.com/questions/15891038/change-data-type-of-columns-in-pandas

### Bootstrap 

https://ocw.mit.edu/courses/mathematics/18-05-introduction-to-probability-and-statistics-spring-2014/readings/MIT18_05S14_Reading24.pdf

https://ocw.mit.edu/courses/mathematics/18-05-introduction-to-probability-and-statistics-spring-2014/readings/MIT18_05S14_Reading23a.pdf

