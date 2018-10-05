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
to make money every time directly from commissions. Therefore **if Vegas is
accurate, on average every team would win 50% of the time against the spread.**

## Results: Are Vegas's NBA spreads accurate?

With [data](http://www.vegasinsider.com/nba/against-the-spread/) on the on 
the win-loss records against the spread for the 2017-2018 NBA season, 
we can calculate how far each team was from 0.500 win record against
the spread and investigate the variation in this data. The **Python code I wrote
to pull, scrub and analyze the data is available** on GitHub as a 
[Jupyter notebook](https://nbviewer.jupyter.org/github/sahildshah1/funData-playground/blob/master/deliverables/nba-spreads.ipynb#)

Here's what the win-loss records against the spread and straight up look like
for the 2017-2017 NBA season: 


![dotplot]({{ site.url }}{{ site.baseurl }}/assets/images/deliverables-nbaspreadsipynb-dotplot.png){: .align-center}


Above is the fraction of total wins straight up and against the spread for all
30 teams in the NBA. If Vegas were perfectly accurate, every team would have a
50% win record (against the spread) and there wouldn't be any variation around
0.5 on the second dot plot. Here's a distribution of how far each team was from
a 0.500 win record.


![histogram]({{ site.url }}{{ site.baseurl }}/assets/images/deliverables-nbaspreadsipynb-hist.png){: .align-center}

Based on this distribution of data, the **average deviation from a 0.500 record
(against the spread) for the 2017-2018 NBA season was -0.013.** Vegas therefore
tended to set the lines slightly too high but  we want to test whether this is
statistically significant.


Rather than make any assumptions about how the deviations from 0.500 are
distributed, we calculate an **empirical bootstrap confidence interval**. 

To learn more about about the empirical bootstrap and how and why it is calculated, see 
[sections 6.3 and 6.4](https://ocw.mit.edu/courses/mathematics/18-05-introduction-to-probability-and-statistics-spring-2014/readings/MIT18_05S14_Reading24.pdf) of
MIT OpenCourseware's Intro to Probability and Statistics (18.05) class notes from
session 24. The 95
percent confidence interval  will correspond to a range of values that are
**not** rejected at a 0.05 significance level. To learn 
more about the relationship between confidence intervals and hypothesis testing
see [section 4](https://ocw.mit.edu/courses/mathematics/18-05-introduction-to-probability-and-statistics-spring-2014/readings/MIT18_05S14_Reading23a.pdf) from MIT OpenCourseware's Intro to Probability and Statistics (18.05) class notes from
session 23a. 
 

Therefore, if 0 fall within the
95 percent confidence interval we would conclude that Vegas is on average
accurate and if 0 falls outside of the 95 percent confidence interval we would
conclude that Vegas is on average inaccurate. After estimating the distribution of  how much the sample mean varies around
an underlying population mean, **we find that the 95 percent confidence interval is [-0.034, 0.006].
Since this range contains 0, we would conclude that Vegas is on average accurate.**


## Methods: Notes on using Python to perform this analysis 

I found these resources helpful for getting started with and using Python to 
perform this analysis: 

- [Selecting subsets of data in Pandas](https://medium.com/dunder-data/selecting-subsets-of-data-in-pandas-6fcd0170be9c)

- [Notes on Python](https://chrisalbon.com/#python)

- [Seaborn examples](https://seaborn.pydata.org/examples/)

- [Stack Overflow issue #47155569](https://stackoverflow.com/questions/47155569/difference-in-plotting-with-different-matplotlib-versions)




