# 🏏 Cricket Score Prediction

A **Machine Learning-based Cricket Score Prediction System** that predicts the final score of a T20 innings based on the current match situation. The project uses ball-by-ball cricket data and applies feature engineering and multiple regression models to predict the final innings score.

## 📌 Project Overview

The model predicts the final score using features such as current score, balls remaining, wickets remaining, current run rate, and runs scored in the last five overs.

- **Type:** Regression
- **Domain:** Sports Analytics
- **Dataset:** ICC Men's T20 World Cup 2024
- **Final Model:** Support Vector Regressor (SVR)
- **Model Selection:** GridSearchCV

## 📊 Dataset

The project uses the **ICC Men's T20 World Cup 2024** ball-by-ball dataset.

<p align="left">
  <a href="https://www.kaggle.com/datasets/pardeep19singh/icc-mens-t20-world-cup-2024">
    <img src="https://img.shields.io/badge/Kaggle-Dataset-20BEFF?style=for-the-badge&logo=kaggle&logoColor=white" alt="Kaggle Dataset">
  </a>
</p>

## 🛠️ Tech Stack

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-Learn
- XGBoost
- Pickle

## ⚙️ Methodology

### Data Preprocessing

- Loaded and cleaned ball-by-ball data
- Handled missing values
- Selected relevant innings
- Removed unnecessary columns
- Extracted city information from the venue

### Feature Engineering

Created important match situation features:

- Current Score
- Balls Left
- Wickets Left
- Current Run Rate
- Runs in Last Five Overs

### Exploratory Data Analysis

Performed:

- Correlation analysis
- Heatmap
- Pairplot
- Feature relationship analysis

### Model Building

Compared multiple regression models using **GridSearchCV**:

- Linear Regression
- Decision Tree Regressor
- Random Forest Regressor
- Support Vector Regressor
- AdaBoost Regressor
- Gradient Boosting Regressor
- KNN Regressor
- XGBoost Regressor

The final model uses **Support Vector Regressor (SVR)** with **One-Hot Encoding** for categorical features and **StandardScaler** for numerical features.

## 📈 Model Evaluation

The model was evaluated using:

- R² Score
- Mean Absolute Error (MAE)
- Mean Squared Error (MSE)

## 🔮 Prediction

A custom `predict_score()` function predicts the final score based on the current match situation.

### Input Features

```text
Innings
Batting Team
Bowling Team
City
Current Score
Balls Left
Wickets Left
Current Run Rate
Last Five Overs Runs
