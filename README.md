# Game Reception Analysis and Prediction

Overview
This project analyzes Steam game data to predict whether a game is well received by the community. Using various features such as Metacritic scores, user scores, playtime statistics, game genres, and platform availability, we build a machine learning model to classify games as well received or not.

# Features
Data Cleaning & Preprocessing: Handles missing values, encodes categorical features, and scales numerical variables.

Feature Engineering: Extracts and encodes multi-label genre data, bins prices, and calculates game age.

Modeling: Utilizes a Random Forest classifier to predict game reception.

Evaluation: Provides classification metrics including accuracy, precision, recall, and F1-score.

Feature Importance: Analyzes which factors most influence the prediction.

# Data
The dataset includes Steam game details such as:

Metacritic and user scores

Player activity metrics (average and median playtime)

Game genres and categories

Platform compatibility (Windows, Mac, Linux)

Price bins

# Usage
Load and preprocess the data (games.csv).

Perform feature engineering including genre encoding and price binning.

Train the Random Forest model on the processed features.

Evaluate model performance on a test split.

Analyze feature importance to understand key drivers.

# Insights
Metacritic score is the strongest predictor of game reception.

Player engagement metrics such as recommendations and playtime also significantly impact predictions.

Game genres and supported platforms contribute but with lower importance.
