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
and statsmodels.\

Data Source:\
To get data on NBA players there are actually a decent amount of resources, but for this project, There were 2 main sources used:
https://www.kaggle.com/drgilermo/nba-players-stats?select=Seasons_Stats.csv and https://www.basketball-reference.com/awards/mvp.html \
The first source is to give us basic stats on all the NBA players from 1950 to 2017, the second provides our MVP voting data since 1955.
