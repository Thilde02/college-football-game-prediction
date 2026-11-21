# college-football-game-prediction
Data analytics capstone project predicting college football game outcomes using historical team performance.
# Predicting College Football Game Outcomes Using Historical Team Performance

## Project Overview

This project examines whether historical college football team performance can help predict the outcome of future college football games.

The project uses historical NCAA Football Bowl Subdivision (FBS) game data from the 2002 through 2025 seasons. The goal is to evaluate whether selected pregame information can help predict whether the home team or away team will win.

## Research Objective

The primary objective is to develop and evaluate machine learning models that predict college football game outcomes using historical team performance and game information.

The prediction target is:

- **Home Win = 1:** The home team wins.
- **Home Win = 0:** The away team wins.

## Data Source

The primary dataset was obtained from the University of Wisconsin public CSV repository:

https://pages.doit.wisc.edu/cewong/public_csv/-/blob/main/cfb_box-scores_2002-2025.csv

The original dataset contains historical college football game information from 2002 through 2025.

The project dataset was filtered to include games in which both teams were classified as FBS participants during the season in which the game was played.

The resulting FBS dataset contains 17,546 games.

## Data Preparation

Data preparation was completed using Microsoft Excel.

The preparation process included:

- Filtering the original dataset to include FBS games.
- Checking for duplicate records.
- Reviewing missing values.
- Creating a binary home-team win outcome variable.
- Calculating historical team winning percentages using games played before the game being evaluated.
- Preparing the data for machine learning analysis.

Final game scores and other in-game statistics were excluded from the predictive features to avoid using information that would not have been available before kickoff.

## Predictive Features

The models use the following eight features:

1. Season
2. Week
3. Game type
4. Away team conference
5. Home team conference
6. Neutral-site indicator
7. Home team's prior winning percentage
8. Away team's prior winning percentage

## Machine Learning Methods

The analysis uses Orange Data Mining to build and evaluate two classification models:

- Logistic Regression
- Decision Tree

These models were selected to compare two different approaches to predicting whether the home or away team would win.

## Training and Testing

A chronological training and testing approach was used.

- **Training data:** 2002–2021 seasons (14,372 games).
- **Testing data:** 2022–2025 seasons (3,174 games).

The models were trained using earlier seasons and evaluated using later seasons. This approach helps assess how the models perform on games from seasons not included in their training data.

## Preliminary Model Results

The initial evaluation produced the following results:

| Evaluation Measure | Logistic Regression | Decision Tree |
|---|---:|---:|
| AUC | 0.670 | 0.552 |
| Accuracy (CA) | 0.631 | 0.565 |
| F1 | 0.620 | 0.567 |
| Precision | 0.623 | 0.568
