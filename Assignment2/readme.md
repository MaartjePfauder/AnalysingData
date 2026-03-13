# Assignment 2 – Linear Regression Analysis

## Overview
This assignment investigates whether different storytelling features can predict the story_score of posts from the ChangeMyView dataset. Simple linear regression was performed on several variables to see which features are good predictors of story strength. The analysis was done in Python using pandas, matplotlib, seaborn and sklearn.

## Research Question
Can any of the following story features predict the story_score?
* agency_score
* event_score
* world_score
* suspense_score
* surprise_score
* curiosity_score

## Method
For each variable the following steps were performed:
* Created scatterplots to visually inspect relationships
* Performed simple linear regression
* Calculated R² scores (both manually and with sklearn)
* Created residual plots
* Performed a Shapiro-Wilk test to check normality of residuals

## Results (short summary)
The results show that event_score and agency_score are the strongest predictors of story_score, both with an R² of around 0.69–0.70. Other variables such as curiosity, suspense and surprise show moderate relationships, while world_score shows a weaker relationship.
