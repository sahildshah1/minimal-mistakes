---
published: true
title: "How many different kinds of NBA players are there?"
---

## Introduction: NBA players 

When sports writer Bill Simmons recently grouped NBA players by 
[how much they were worth seeing live](https://www.theringer.com/the-bill-simmons-podcast/2018/12/14/18140197/kathryn-hahn-on-the-harden-trade-and-step-brothers)
and by [how much they were worth in a trade to other NBA teams](http://tradevalue.theringer.com/), it made me curious what a data driven grouping of **how NBA players 
performed** in the 2017-2018 season would elucidate about the archetypes that
played in the NBA last year.  

In my analysis, I use three  player stats (Points Per Game, Total Rebounds Per
Game, and Assists per Game) and a machine learning algorithm (K-Means) to group
players by their performance resulting in a  clustering that is  driven entirely
by the data.  When Bill Simmons grouped players by trade value, he took into
account data such as salary, age, and contract length, but ultimately
constructed the groupings by hand. If I used stats from a different year (I use
data from the 2017-2018 season), the clusters could be different since both the
dynamics of the game and the roles individual players play on their team changes
over time.


## Results: How many different kinds of NBA players are there?

With [data](https://www.basketball-reference.com/leagues/NBA_2018_per_game.html)
on per game stats for 469 NBA players from the 2017-2017 season, I used K-Means
to cluster NBA players and interrogate the number and kind of archetypes that
played in the NBA last year. The **Python code I wrote to pull, scrub, and
analyze the data is available** on Github as a 
[Jupyter notebook](https://nbviewer.jupyter.org/github/sahildshah1/funData-playground/blob/master/deliverables/nba-players.ipynb)


Here's what Points Per Game (PS/G), Total Rebounds Per Game (TRB), and Assists
per Game (AST) look like for the 2017-2018 NBA season:

![dotplot]({{ site.url }}{{ site.baseurl }}/assets/images/deliverables-nbaplayersipynb-splom.png){: .align-center}

Above is a scatter plot matrix of PS/G, TRB, and AST for 469 players for the
2017-2018 NBA season. Note that each stat is on a different scale. Before 
clustering the players using K-Means, I center and scale each statistic by
removing the mean value and dividing by the standard deviation. 

After applying K-Means to the centered and scaled data, we found three clusters.
To learn more about K-Means, see 
[here.](https://scikit-learn.org/stable/modules/clustering.html#k-means)
For details on how I selected
the number of clusters, see the Methods section below. Players were clustered
according to the role they tended to play  on their team for the 2017-2018
season resulting in three archetypes which  we call Play makers, Shot takers,
and Role players:

### Group A: Play makers

- Representative players: LeBron James, Ben Simmons, J.J. Redick
- Group A average stats: 17.27 PS/G - 4.54 TRB - 5.31 AST

### Group B: Shot takers

- Representative players: Klay Thompson, Robert Covington, Kelly Olynyk
- Group B average stats: 12.71 PS/G - 5.92 TRB - 1.90 AST

### Group C: Role players
- Representative players: J.R. Smith, Danny Green, Andre Iguodala
- Group C average stats: 5.23 PS/G - 2.24 TRB -  1.23 AST 

<!-- Role players play less minutes on average -->


We therefore find  three archetypes which  we call Play makers, Shot takers, and
Role players that played in the 2017-2018 NBA season.

<!-- Note that players assigned as Shot takers tended to drive to the basket or
pull up and shoot more often than distribute the ball last year on their 
specific team, but those players could have the ability to be Play makers 
and distribute the ball.  -->

<!-- 
What's the break down of groups for Warriors teams, Cavs, All Star teams?
 -->


## Methods: Notes on using K-Means and Python to perform this analysis 

### Selecting the number of clusters using model inertia and silhouette coefficients

Since we have to specify the number of groups to cluster the data into before
applying K-Means and we don't know the number of groups a priori, we use the
model inertia (within-cluster sum-of-squares) and silhouette coefficient to
determine the number of clusters.
Here's what the inertia and silhouette look
like for K = 1 to K = 10 clusters. Note that the silhouette isn't defined 
for K = 1 cluster. 

![dotplot]({{ site.url }}{{ site.baseurl }}/assets/images/deliverables-nbaplayersipynb-elbow.png){: .align-center}


To learn more about the silhouette coefficient,
see [here.](https://scikit-learn.org/stable/auto_examples/cluster/plot_kmeans_silhouette_analysis.html)

<!-- 
K Means function arguments

K means algorithm and Lloyd's algorithm?
 -->

### Helpful resources 

I found these resources helpful for getting started with and using Python to 
perform this analysis: 

- [Numpy tutoriall](https://docs.scipy.org/doc/numpy/user/quickstart.html)
- [Pyplot tutorial](https://matplotlib.org/1.3.1/users/pyplot_tutorial.html)
- [Matplotlib Gallery](https://matplotlib.org/gallery/index.html)


<!-- [Scikit learn Clustering](https://scikit-learn.org/stable/modules/clustering.html#clustering)

https://stackoverflow.com/questions/36367986/how-to-make-inline-plots-in-jupyter-notebook-larger

https://stackoverflow.com/questions/42314542/python-how-to-append-numpy-array-to-a-pandas-dataframe
 -->



