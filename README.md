# nbritto795.github.io


# Ending the Debate - The Top 10 NBA Players of All-Time

Analyzing all NBA players since 1950 and looking at their lifetime stats to determine who the greatest
players are using MVP voting as the standard.


## Introduction

The debate of who the best NBA player ever is a contentious one - some say LeBron, some say MJ and 
some say old school players like Wilt Chamberlin or Kareem Abdul-Jabbar. Regardless of the opinion,
Different people have reasons for their top pick: most dominant, most points, most championships.
Today we will be exploring who the top 10 NBA players are using data and machine learning. There
will undoubtedly be some subjectivity, but the goal will be to explore some of the top players and
use MVP voting from the last ~30 years to determine which attributes are the most valuable and what
combination of stats and advanced stats make up the most valuable players. Using these learnings,
we will create a top 10 list!
## Part 1 - Data Curation
Setup:\
First we import the libraries that we will need, this includes pandas, matplotlib, seaborn, sklearn,
and statsmodels.

Data Sources:\
To get data on NBA players there are actually a decent amount of resources, but for this project, There were 2 main sources used:
https://www.kaggle.com/drgilermo/nba-players-stats?select=Seasons_Stats.csv and https://www.basketball-reference.com/awards/mvp.html \
The first source is to give us basic stats on all the NBA players from 1950 to 2017, the second provides our MVP voting data since 1955, which will provide data for our model to train and test on.\ This project mostly focuses on more basic stats (points, rebounds, assists), however some advanced statistics are explored. If you are not knowledgeable about these or you would simply like to learn more, I recommend reading this medium post: https://medium.com/@shahinourian/nba-advanced-stats-101-5aedf7d6072 for a good  explanation.

## Part 2 - Parsing and Management
To house the data I decided to use dataframes. Once the data was in a dataframe, the main objective was to reduce the amount of players, we started with almost 25,000 players and to do any analysis and or visualization reducing the dataset was necessary. First, I began by cleaning the data, any records with major stats (steals, blocks, turnovers, rebounds) that had a null value were removed from the dataset. At this point, I wanted to isolate the top players of the dataset and since points are one of the most important factors in winning a basketball game, the ability to score those points is very important. Eliminating any player that has not been able to average more than 20 pts in any one season. An important note is that the data we are working with contains data from each player on a season basis. Later on we consolidated the data taking the career averages of players and eliminated any player that did not have a career average of 20+ points.

## Part 3 - Exploratory Data Analysis
Analyzing the data yielded some interesting finds. I looked at the breakdown of our resulting players from the previous section and found that the highest concentration of players came from the shooting guard position (SG). Looking at the Most Valuable Player (MVP) voting dataset, we were able to see all of the players that were in the running for the MVP award along with their final ranking when the voting ended. We looked at all the MVP winners and what their stats looked liked in comparison and went on to see which stats were more important for the award by looking at a correlation matrix.

## Part 4 - Hypothesis Testing and Machine Learning
The null hypothesis for this experiment was that none of the stats had a significant impact on the MVP vote ranking. The null hypothesis was rejected because the p-value for specific stats were less than the significance level. The analysis was done using Ordinary Least Squares Regression and a linear regression. The machine learning aspect was done by performing a linear regression on our data and then fitting it to our training set and testing it with our testing set. I did this with a random forest classifier as well to provide 2 different lists. For more information on random forests and decision trees see this link: https://towardsdatascience.com/decision-trees-and-random-forests-df0c3123f991 \
Once I had trained my data and tested it to look at the accuracy, I then shifted my focus to predicting the top 10 players. I took the dataset I had from earlier with the complied career stats and using career stats, I predicted their rank. In this case the lowest rank would mean the best player.

## Part 5 - Insights
The results from the linear regression predictions:
1. LeBron James\
2. Michael Jordan\
3. David Robinson\
4. Kevin Durant\
5. Larry Bird\
6. Karl Malone\
7. Charles Barkley\
8. James Harden\
9. Stephen Curry\
10. Anthony Davis\

This is a respectable list and though it differs from my personal opinion, there were some interesting takeaways when building this. First, was the breakdown of the stats and which ones impacted the rank the most. Interestingly it wasn't points, it was an advanced statistic called win shares per 48 which is a metric that estimates the number of wins a player produces for their team. This makes sense as winning games is the ultimate goal and the ability to provide your team with wins on a 48 minute basis analyzes the most efficient helpful players. This is backed up by history as only 2 players have ever won the MVP award with a team that had a losing record. Other important stats were points scored per game rebounds, assists, and blocks. \Interestingly, stats such as percentages (field goal percentage) were not big influencers and point to the idea that players don't necessarily have to be the most efficient to be the most valuable player, they need to have output and win games. In the end, the players with the highest win shares and highest point, rebound and assist averages topped the list. Another interesting find was that there were many players with high point averages that did not have a high win share per 48. This would indicate that although the player was scoring points they were not helping their team win, this could be because they are very inefficient when it comes to scoring, that they are able to score but do not make their team better, or that their surrounding team is not very good.\
Another observation during the linear regression analysis was the low R-squared value, this indicates that our predicted values don't correlate exactly with the actual values. This was one of the reasons I decided to go with a non-linear method as well and use a random forest to attempt to come up with a top 10 list, however this as well did not result in the highest accuracy either given my inputs. The lack of correlation could be due to a number of factors. A plausible explanation is that the MVP award is decided by the media and they don't always vote for the statistically best player, it is a subjective decision sometimes and things like season-long storylines and biases will affect who votes for who. Regardless, it must be acknowledged that this analysis is not perfect and the correlation does not indicate that the features predict the MVP rank perfectly, however, I think the analysis shows each of the stats previously mentioned are significant and do influence how valuable a player is in the eyes of the media. If I had more time, I would have liked to explore different hyperparameters and other machine learning techniques to see if I could get a better predictive method.