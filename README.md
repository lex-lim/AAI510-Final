## Video Games Success Prediction Model

This project aims to predict whether a video game is "well received" based on a combination of quantitative metrics, platform availability, tags, genres, pricing, and engagement features. It leverages a Random Forest classifier with extensive feature engineering and includes a special analysis on ethically questionable game design elements.

# Dataset
Source: Steam Games Dataset on Kaggle

Preprocessing: Rows with insufficient reviews (Total_Reviews < 10) were excluded to ensure reliability.

# Target Definition
A game is considered well received if at least 2 out of 3 criteria are met:

Positive review ratio ≥ 70%

Metacritic score ≥ 70

User score ≥ 80

The resulting binary label (Well_Received) is used as the prediction target.

# Data Preprocessing
Dropped problematic or low-value entries.

Created new variables such as:

Total_Reviews, Pos_Ratio, Game Age

One-hot encoded platform and pricing data.

Converted Genres and Tags into binary indicator columns using MultiLabelBinarizer.

Filtered out infrequent tags (appearing in <3 games).

Engineered playtime ratio metrics as engagement signals:

Avg_Playtime_Ratio_Recent_Forever

Med_Playtime_Ratio_Recent_Forever

Scaled numerical features using StandardScaler.

# Exploratory Data Analysis
Distribution of review scores

Scatter and boxplots for user and critic scores by reception

Genre distribution and ranking by "well-received" rate

# Modeling
Baseline Model
Model: RandomForestClassifier (100 trees)

Performance:

Accuracy ~93%

Key features: Metacritic score, Recommendations, Playtime

# Hyperparameter Tuning
Conducted GridSearchCV to optimize the Random Forest.

Metrics: f1_weighted

Best model improved performance and provided refined feature importances.

# No Metacritic Variant
A second model was trained excluding Metacritic score.

Accuracy dropped (~67%), highlighting its predictive strength but also emphasizing the influence of other features.

# Ethical Tag Analysis
The model inspects tags associated with potentially problematic design elements such as:

Grind, Pay to Win, Loot Box, Casino, Addictive, etc.

These features were included to assess how such mechanics relate to public reception. Their importances were examined to avoid unintentional reinforcement of unethical patterns.

# Dependencies
pandas, numpy, matplotlib, seaborn

scikit-learn

collections

# Future Work
Incorporate text-based sentiment analysis from user reviews.

Try more advanced models (e.g., XGBoost, SHAP explanations).

Extend ethical feature tracking and detection.
