# Regression Project Proposal

## Question/Need:

I intend to examine NBA statistics to create a linear regression model that can predict a player's salary contract. NBA teams can benefit from my model by being able to offer competitve salary contracts based on performance metrics. This will be useful in application to players with expiring contracts, or to teams involved in trade negotiations.

## Data Description:

As of now, I plan to rely heavily on https://www.basketball-reference.com/ and espn.com to obtain current and historical data. I will use web-scraping methods to clean and gather the data for analysis. An individual unit of analysis would be an NBA player. I'll be examining a player's current contract amount and career statistics, and compare with these with league averages.

I plan to rank the player's career statistics and salary against the rest of the league by percentile. I feel this will be a scalable way to address the variation of distributions from year-to-year. The NBA in recent years has become more offense-centric, with the increased popularity around 3-point shooting. Salary caps have been consistently increasing year over year.

The features I am interesting in using are NBA boxscore statistics (Points per game, rebounds, assists etc.) One of my primary goals is to determine which feature has the strongest effect on salary amount. Time permitting, I plan to also create separate models for each position (PG, SG, SF, PF, C) as certain stats have different value depending on position.

Some of my predicts are that PPG and shooting% will be strong predictors of salary overall. Assist and/or assist-to-turnover ratio may play an important factor for guards. Blocks and Rebounds should be strong factors for the center position.

## Tools:

I plan to use BeautifulSoup/Selenium to web scrape my data. I'll use statsmodels/sklearn for EDA and to create my linear regression. I'll use visualization tools to plot my linear regression. I plan to use new tools if they are applicable to my project goal.

## MVP Goal:

My MVP goal is to create a model that can predict a value of an NBA player. I hope to produce a model with a high level of confidence on predicting power. I'll likely use my model and apply it to at least one specific player to determine his future contract value.

### Feedback:

Feedback is greatly appreciated! Specifically any feedback on how I can focus my regression project to fit the time contraints. I am concerned about setting overambitious goals and not meeting deadlines!


```python

```
