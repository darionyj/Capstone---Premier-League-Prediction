# Capstone---Premier-League-Prediction

## Summary
Football is the most popular sports in the world. It is mostly dominant in Europe, South America and Africa. Countries in these continents have their own football leagues at home. An example will be the English Premier League from England. The league has 20 teams every season and whenever the season ends, the bottom three teams will be relegated to the league below them which is the English Football League. Then, the top three teams from English Football League will be promoted to the Premier League. 

## Problem Statement

We will be predicting the football matches result in the English Premiear League. As football matches are always full of surprises, we will be using past matches data and data from FIFA game series. With these data and analysis, our model will be able to assist potential stakeholders such as football pundits, betting website, football fans and shareholders of football clubs. 

Our goal is to predict the result, home total goals and away total goals.

In this project, there will be a total of seven notebooks:
1) Part 1A - Data Acquisition
2) Part 1B - FIFA & Season Fixtures Clean Up
3) Part 2 - Data Preparation, EDA & Feature Engineering
4) Part 3 - Modeling for Result
5) Part 4A - Modeling for Home Total Goals
6) Part 4B - Modeling for Away Total Goals
7) Part 5 - Predictions & Conclusion

1. [Datasets Used](#1-Datasets-Used)
2. [Exploratory Data Analysis & Data Cleaning](#2-Exploratory-Data-Analysis-&-Data-Cleaning)
3. [Modeling & Evaluation](#3-Modeling-&-Evaluation)
4. [Conclusion & Improvements](#4-Conclusion-&-Improvements)
5. [Python Library Used](#5-Python-Library-Used)

## Data Used
We will be using two types of data. 
1) Football Match Fixtures which will be scraped from [FBREF](https://fbref.com/en/comps/9/schedule/Premier-League-Scores-and-Fixtures)
2) FIFA Game Players Stats will be taken from [Kaggle](https://www.kaggle.com/stefanoleone992/fifa-21-complete-player-dataset)

The following are the csv used:
- epl2018
- epl2019
- epl2020
- epl2021
- epl2021_prediction
- players_18
- players_19
- players_20
- players_21
- bpl2018_clean
- bpl2019_clean
- bpl2020_clean
- bpl2021_clean
- bplteamstats2018_clean
- bplteamstats2019_clean
- bplteamstats2020_clean
- bplteamstats2021_clean
- combined_final
- predict_fixtures

### 2. Exploratory Data Analysis & Data Cleaning
In this section, we undergo studying, understanding and feature engineering of the datasets. After that, datasets were combined. The following actions are taken:
- Analyzing the fifa players stat. Feature Engineering of players and teams
- Analyzing the fixtures datas. Feature Engineering of result feature, past match stats average, total goals. Combining fixtures and team stats.
- Analyze the Combined Datasets and understand the corrrelation between some features.

### 3. Modelling & Evaluation
Several classifier models were developed, where the hyperparameters were tuned for each model to obtain the best f1_micro scores. MinMaxScaler were used to scale all data. As home total goals and away total goals classes are imbalanced, an over-sampling method known as SMOTE (Synthetic Minority Over-sampling Technique) was adopted. Models picked up are Random Forest for Result, Gradient Boost for Home Total Goals and Support Vector Classifier for Away Total Goals. There is a slight overfit in the scores in the model for Result. However, for the Home Total Goals and Away Total Goals, there is a large overfit and very bad test scores.

Models used:
- Logistic Regression
- Random Forest Classifier
- ExtraTrees Classifier
- AdaBoost Classifier
- Gradient Boost Classifier
- Support Vector Classifier

Evaluation Metrics used:
- F1-Score
- Recall
- Precision
- Accuracy

### 4. Conclusion & Improvements
In this project,we understand the usage of machine learning for predicting football results.  Using the data and Random Forest Classifier, we are only able to get 53% accuracy and F1-Score for the result prediction. Additionally, for home and away goals predictions,we are only able to get 31.2% by using Gradient Boosting and 32.2% by using Support Vector Classifier. Both of the scores are lower than the baseline.

Despite only getting 50% accuracy, it might not be a bad thing as there is more than 50% chance to getting the right result. However, football prediction is not as easy as it seems to be. There are other factors that might come into play and affect the final result, even if we have all the data necessary and able to predict 100%. Other factors include match-fixing, players injuries, match postponement, fatigue, etc.

For the future, I will like to get more data like events during a match, such as a shot on target at 30 min, or a goal by home team at 40 min before half time, or after half time. Other data includes more players data or player-to-player data. With these data, I will be able to explore on more other targets such as halftime and full time scores, which team to score first, which player to score first, number of corners, number of yellow cards and etc.

### 5. Python Library Used
- Pandas
- Numpy
- Seaborn
- Matplotlib
- Pickle
- Sklearn
- Imblearn
- Itertools
- Graphviz
- Os
- Time
- Csv
- Glob
- Warnings
- IPython.display
