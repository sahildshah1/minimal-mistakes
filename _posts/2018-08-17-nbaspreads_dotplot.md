---
published: true
title: "Are Vegas's NBA spreads accurate?"
---

## Introduction: What are NBA spreads?

When sports betting was [legalized](https://www.nytimes.com/2018/05/14/us/politics/supreme-court-sports-betting-new-jersey.html) this 
summer, it sparked a debate amongst my friends about whether Vegas is accurate
in setting spreads over the course of a season across the NBA  (or if there's a bias that we
could theoretically exploit to `beat the house.')

In addition to taking bets on whether a team will win or lose straight up, Vegas
also offers a `spread' that handicaps the favored team. Vegas wants to set the point
spreads so that the chance of a team winning or losing is 50-50. This
incentivizes an equal number of bets on both sides of the bet and allows Vegas
to make money every time directly from commissions. Therefore if Vegas is
accurate, on average every team would win 50% of the time against the spread.

## Results: Are Vegas's NBA spreads accurate?

With data on the on the win-loss records against the spread for the 2017-2018
NBA season, we can calculate how far each team was from 0.500 win record against
the spread and investigate the variation in this data. I performed this analysis
using Python 3 in a Jupyter notebook: 



Here's a dot plot of each team's record straight up and against the spread.

![dotplot](/assets/images/deliverables-nbaspreadsipynb-dotplot.png?raw=true){:.center-image}


Here's a distribution of how far each team was from a 0.500 win record. 

![histogram](/assets/images/deliverables-nbaspreadsipynb-hist.png?raw=true){:.center-image}


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

Since this range contains 0, we would conclude that Vegas is on average accurate.


## Methods: Notes on using Python to perform this analysis 

I found these resources helpful for getting started with and using Python to 
perform this analysis: 

- [Selecting Subsets of Data in Pandas](https://medium.com/dunder-data/selecting-subsets-of-data-in-pandas-6fcd0170be9c)

- [Technical notes on Python](https://chrisalbon.com/#python)

- [Seaborn examples](https://seaborn.pydata.org/examples/)

- [Stack Overflow issue #47155569](https://stackoverflow.com/questions/47155569/difference-in-plotting-with-different-matplotlib-versions)








