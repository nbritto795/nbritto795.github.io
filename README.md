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
The first source is to give us basic stats on all the NBA players from 1950 to 2017, the second provides our MVP voting data since 1955, which will provide data for our model to train and test on.\ This project mostly focuses on more basic stats (points, rebounds, assists), however some advanced statistics are explored. If you are not knowledgeable about these or you would simply like to learn more, I recommend reading this medium post: https://medium.com/@shahinourian/nba-advanced-stats-101-5aedf7d6072 for a decent explanation.

## Part 2 - Parsing and Management
To house the data I decided to use dataframes. Once the data was in a dataframe, the main objective was to reduce the amount of players, we started with almost 25,000 players and to do any analysis and or visualization reducing the dataset was necessary. First, I began by cleaning the data, any records with major stats (steals, blocks, turnovers, rebounds) that had a null value were removed from the dataset. At this point, I wanted to isolate the top players of the dataset and since points are one of the most important factors in winning a basketball game, the ability to score those points is very important. Eliminating any player that has not been able to average more than 20 pts in any one season. An important note is that the data we are working with contains data from each player on a season basis. Later on we consolidated the data taking the career averages of players and eliminated any player that did not have a career average of 20+ points.

## Part 3 - Exploratory Data Analysis
Analyzing the data yielded some interesting finds. I looked at the breakdown of our resulting players from the previous section and found that the highest concentration of players came from the shooting guard position (SG). Looking at the Most Valuable Player (MVP) voting dataset, we were able to see all of the players that were in the running for the MVP award along with their final ranking when the voting ended. We looked at all the MVP winners and what their stats looked liked in comparison and went on to see which stats were more important for the award by looking at a correlation matrix.

## Part 4 - Hypothesis Testing and Machine Learning
