---
published: true
title: "What stats should Stever Kerr look at?"
---

## Introduction: Steve Kerr -- Head Coach of the Golden State Warriors (GSW)

In an [interview with The Ringer's Bill Simmons](https://www.reddit.com/r/nba/comments/8hh0kt/ocsteve_kerr_said_the_most_important_boxscore/) last 
year, Steve Kerr said "I look at the  opponent's field goal percentage, 
our assists, and our turnovers. Those are the three numbers... If we defend 
and take care of the ball we win. And it's  generally the case, and those three 
numbers usually tell the story."

In this post, I identify the stats most important for predicting a GSW
win or loss using the machine learning model [Random forests.](https://en.wikipedia.org/wiki/Random_forest) 

<!-- to statistically determine which stats Steve Kerr should
be looking at. 
 -->   
The **Python code I wrote to pull, scrub, and  analyze the data is available**
on Github as a [Jupyter
notebook](https://nbviewer.jupyter.org/github/sahildshah1/funData-playground/blob/master/deliverables/GSWGameLog.ipynb?flush_cache=true)


## Results: What stats should Stever Kerr look at?

With [GSW game logs](https://www.basketball-reference.com/teams/GSW/2016/gamelog/) 
from the 2015, 2016, and 2017 seasons, I investigated which team stats were
most predictive of GSW wins. With the game logs, I constructed a dataset of
16 team and opponent stats for 246 regular season games. 

I built a predictive model using Random forests, where the inputs (or predictors)
are the team and opponent stats and the output (or response) is either a GSW
win or loss. Using cross-validation to evaluate the model's performance, the
[accuracy of the model](https://en.wikipedia.org/wiki/Accuracy_and_precision#In_binary_classification) is 89%.

Random forests models provide for a quantification of predictor importance
called "feature importance." The higher 
the value of "feature importance" the more important it is to the prediction
function. We can therefore interpret the stats with the highest "feature importance"
as most important for predicting a GSW win or loss.

![]({{ site.url }}{{ site.baseurl }}/assets/images/GSWGameLog-bar.png){: .align-center}

Above is a horizontal bar plot of feature importance for 16 different stats 
arranged from most important (at the top) to least important (at the bottom).
According to this  analysis, the variables most important for predicting
a GSW win or loss are Team (GSW) FG% (Field Goal %) and Team (GSW) 3P% (3 Point %) followed by Opponent FG% 
and Team (GSW) AST (Assists). Steve Kerr should therefore be looking at not only the 
opponents FG% and his team's AST but also how well the GSW are shooting.  


## Methods: Notes on using Random Forests to perform this analysis 

Random forests are a collection of decision trees. To read more about decision trees and random forests,
see [here](https://drive.google.com/file/d/1oma2KF-FnkC4M2D0ThoQMsdLLT-H2bw3/view).

<!-- https://stackoverflow.com/questions/8961586/do-i-need-to-normalize-or-scale-data-for-randomforest-r-package

Scaling is done to Normalize data so that priority is not given to a particular feature. Role of Scaling is mostly important in algorithms that are distance based and require Euclidean Distance.

Random Forest is a tree-based model and hence does not require feature scaling. -->

The main hyper-parameters of the random forests model are the number of trees
to grow and the number of features to consider when splitting a
node. To read more about these parameters, see [here.](https://scikit-learn.org/stable/modules/ensemble.html#parameters) In this analysis,
I chose default values for these hyper-parameters rather than choose the values that yield the best performance as evaluated with cross-validation. 

Feature importance is quantified using the concept of "node purity." To read
more about node purity, see [here.](https://towardsdatascience.com/what-is-a-decision-tree-22975f00f3e1) Features that result in more "pure" nodes are considered more important. To read more about feature importance, see [here.](https://scikit-learn.org/stable/modules/ensemble.html#feature-importance-evaluation)

<!-- 
 "A node is 100% impure when a node is split evenly 50/50 and 100% pure when all of its data belongs to a single class."  -->

<!-- 
** How is it computed: ** 

https://scikit-learn.org/stable/modules/ensemble.html#feature-importance-evaluation

" In scikit-learn, the fraction of samples a feature contributes to is combined with the decrease in impurity from splitting them to create a normalized estimate of the predictive power of that feature." References:

[L2014]	G. Louppe, “Understanding Random Forests: From Theory to Practice”, PhD Thesis, U. of Liege, 2014. 
See: https://medium.com/the-artificial-impostor/feature-importance-measures-for-tree-models-part-i-47f187c1a2c3

---> Samples a feature contributes to combined with purity by weighing Weight decrease in node impurity by number of samples it splits  -->

<!-- ## Helpful resources: 

https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.plot.bar.html
 -->
