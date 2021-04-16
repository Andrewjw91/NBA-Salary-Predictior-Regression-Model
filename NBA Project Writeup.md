# Predicting NBA Player Salaries Using Regression Models

## Abstract

The goal of my project was to use regression models on NBA performance statistics to predict player salaries. Through the process of exploratory data analysis, feature engineering, and model testing/selection, I was able to determine the basketball statistics that were most correlated to an increase in salary.

## Design

This project uses the NBA player statistics data from basketball-reference.com and salary data from hoopshype.com. In identifying the NBA stats with the highest effect on salary, this can provide insight into which skills a player should improve in order to land a larger contract. Additionally, the model findings can enable NBA teams to have a baseline for the valuation of a player. Teams can determine the projected valuation of a player's next contract based on performance.

## Data

The dataset contains 4590 rows of player data from the last 10 NBA Seasons (2021-2012). There are 28 feature columns, 3 of which are categorical. The numerical features are the standard NBA Box Score performance stats that are recorded after each game, which include season averages of shooting percentages, rebounds, points, assists, steals etc. Many of the features were multicollinear results of other columns, for example Field Goals = Field Goals Attempted * FG%.

## Algorithms

#### Feature Engineering:

1. Removing Multicollinear or redundant shooting percentage-based stats
2. Converting categorical 'Pos' columns into binary dummy variables
3. Assigning players with a combo position (e.g PF/C) to the first position listed (PF)
4. Creating a new feature column using an Approximate Value ('AV') formula as a performance metric.
Credits Formula = (Points)+(Rebounds)+(Assists)+(Steal)+(Blocks)-(Field Goals Missed)-(Free Throws Missed)-(Turnovers)
AV Formula = (Credits**(3/4) )/21

#### Models:

-Simple Linear Regression
-Polynomial Regression with a degree = 2
-Lasso Cross Validation
-Ridge Regression

#### Model Evaluation and Selection:

The entire training dataset was split into a 80/20 train-test holdout.

Simple Linear Regression R2 on test data: 0.575
Polynomial Regression R2 on test data: 0.682
Lasso Cross Validation R2 on test data: 0.649
Ridge Regression R2 on test data: 0.568

I chose Polynomial Regression as my preferred model. The polynomial transformation of degree 2 placed higher weight on coefficients (e.g. PTS, FT, AST) with larger value ranges and larger variance. This conversely decreased the weight of stats such as STL and TOV when polynomial transformation was applied.

Although the Ridge Regression results were similar to that of the Linear Regression model, the evaluation of the standardized scaled coefficients provided some useful insight into the beta weights of the coefficients. The Turnover stat (TOV) had a negative coefficient value, which makes sense since this is a detrimental stat. PTS, AST, and TRB had high effect on Salary, given that these are amoung the most valuable offensive and defensive metrics. Minutes Per Game (MP) had a negative coefficient value, likely due to the fact that the majority of bench players see far less playing time despite getting paid a minimum base salary.

## Tools

Numpy, Pandas for data manipulation
Scikit-learn for modeling
Matplotlib and Seaborn for plotting and visualization
