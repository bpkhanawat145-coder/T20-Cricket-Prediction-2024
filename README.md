# 🏏 T20 Cricket Score Prediction

A **Machine Learning-based Cricket Score Prediction System** that predicts the final score of a T20 innings using the current match situation.

The project uses historical ball-by-ball cricket data, feature engineering, exploratory data analysis, multiple regression models, and hyperparameter tuning.

---

## 📌 Project Overview

The model predicts the **final innings score** using:

* 🏏 Batting team
* 🎯 Bowling team
* 📍 City
* 📊 Current score
* ⏳ Balls remaining
* 🧤 Wickets remaining
* 📈 Current run rate
* 🔥 Runs scored in the last five overs

| Category            | Details                        |
| ------------------- | ------------------------------ |
| **Type**            | Regression                     |
| **Domain**          | Cricket / Sports Analytics     |
| **Dataset**         | ICC Men's T20 World Cup 2024   |
| **Target**          | Final Innings Score            |
| **Final Model**     | Support Vector Regressor (SVR) |
| **Model Selection** | GridSearchCV                   |
| **Evaluation**      | R² Score, MAE, MSE             |

---

## 📊 Dataset

The project uses the **ICC Men's T20 World Cup 2024** ball-by-ball cricket dataset from Kaggle.

🔗 **Dataset:** [ICC Men's T20 World Cup 2024](https://www.kaggle.com/datasets/pardeep19singh/icc-mens-t20-world-cup-2024)

The dataset contains information such as:

* Match ID
* Innings
* Batting Team
* Bowling Team
* Venue
* Ball number
* Runs
* Extras
* Wickets
* Players involved

Only the **1st and 2nd innings** are used for the prediction task.

---

## 🛠️ Tech Stack

* **Python**
* **Pandas & NumPy** – Data processing
* **Matplotlib & Seaborn** – Data visualization
* **Scikit-Learn**

  * Linear Regression
  * Decision Tree Regressor
  * Random Forest Regressor
  * Support Vector Regressor
  * AdaBoost Regressor
  * Gradient Boosting Regressor
  * KNN Regressor
  * GridSearchCV
  * Pipeline
  * ColumnTransformer
  * OneHotEncoder
  * StandardScaler
* **XGBoost**
* **Pickle**

---

## ⚙️ Methodology

### 1. Data Preprocessing

The dataset was explored for:

* Dataset shape
* Column names
* Data types
* Missing values
* Statistical summary
* Unique values

Unnecessary columns were removed and missing values in run-related columns were replaced with `0`.

### 2. Feature Engineering

Important match situation features were created:

| Feature            | Description                               |
| ------------------ | ----------------------------------------- |
| `current_score`    | Cumulative score during the innings       |
| `balls_left`       | `120 - balls_bowled`                      |
| `wicket_left`      | `10 - player_dismissed`                   |
| `current_run_rate` | `(current_score × 6) / balls_bowled`      |
| `last_five`        | Runs scored in the previous 30 deliveries |
| `city`             | Extracted from venue                      |

---

## 📋 Final Features

```text
innings
batting_team
bowling_team
city
current_score
balls_left
wicket_left
current_run_rate
last_five
runs_x
```

`runs_x` represents the **final innings score**, which is the prediction target.

---

## 📈 Exploratory Data Analysis

The project includes visualizations such as:

* Runs by batting team
* Wickets left vs. runs
* Current score vs. run rate
* Pairplot
* Correlation matrix
* Correlation heatmap

These visualizations help understand the relationship between match situation features and the final score.

---

## 🤖 Model Building

The dataset was divided into **80% training and 20% testing** data.

### Categorical Features

The following features were processed using **OneHotEncoder**:

* `batting_team`
* `bowling_team`
* `city`

### Numerical Features

The following features were standardized using **StandardScaler**:

* `innings`
* `current_score`
* `balls_left`
* `wicket_left`
* `current_run_rate`
* `last_five`

The preprocessing steps were combined using a Scikit-Learn **Pipeline**.

---

## 🔍 Models Compared

The following regression models were compared:

* Linear Regression
* Decision Tree Regressor
* Random Forest Regressor
* Support Vector Regressor
* AdaBoost Regressor
* Gradient Boosting Regressor
* KNN Regressor
* XGBoost Regressor

**GridSearchCV with 5-fold cross-validation** was used for hyperparameter tuning and model comparison.

---

## 🏆 Final Model

The final model selected is **Support Vector Regressor (SVR)**.

### Parameters

```text
C = 5
kernel = rbf
gamma = scale
```

The preprocessing and prediction steps are combined into a single Machine Learning pipeline.

---

## 📊 Model Evaluation

The model is evaluated using:

* **R² Score**
* **Mean Absolute Error (MAE)**
* **Mean Squared Error (MSE)**

The predicted scores are compared with the actual final innings scores.

---

## 🔮 Prediction

A custom `predict_score()` function is used to predict the final score from the current match situation.

### Example

```python
predict_score(
    1,
    'Canada',
    'United States of America',
    'Dallas',
    49.0,
    90,
    10,
    9.8000,
    49
)
```

The notebook also tests different match situations, including:

* 🇿🇦 South Africa vs India
* 🇦🇫 Afghanistan vs Uganda

---

## 💾 Model Serialization

The trained pipeline is saved using **Pickle**:

```python
pickle.dump(
    pipeline,
    open('pipeline.pkl', 'wb')
)
```

This allows the trained model to be reused without retraining.

---

## 🔄 Machine Learning Workflow

```text
Ball-by-Ball Data
       ↓
Data Preprocessing
       ↓
Feature Engineering
       ↓
Exploratory Data Analysis
       ↓
Train-Test Split
       ↓
Encoding + Scaling
       ↓
Multiple Regression Models
       ↓
GridSearchCV
       ↓
Model Comparison
       ↓
SVR Final Model
       ↓
Score Prediction
       ↓
Save Model
```

---

## 🚀 Key Features

* 🏏 T20 Cricket Score Prediction
* 📊 Ball-by-Ball Data Analysis
* ⚙️ Match Situation Feature Engineering
* 📈 Current Score & Run Rate Calculation
* ⏳ Balls Remaining Calculation
* 🧤 Wickets Remaining Calculation
* 🔥 Last Five Overs Analysis
* 📉 Exploratory Data Analysis
* 🤖 Multiple Regression Models
* 🔍 Hyperparameter Tuning with GridSearchCV
* 🔄 Scikit-Learn Pipeline
* 🎯 Final Score Prediction
* 💾 Model Serialization

---

## 🎯 Learning Outcomes

This project demonstrates practical experience in:

* Data Cleaning
* Feature Engineering
* Exploratory Data Analysis
* Regression
* Feature Encoding & Scaling
* Machine Learning Pipelines
* Hyperparameter Tuning
* Cross-Validation
* Model Comparison
* Model Evaluation
* Model Serialization

---

## 📁 Project Structure

```text
T20-Cricket-Score-Prediction/
│
├── ML_Project_Cricket_Score_Prediction.ipynb
├── deliveries.csv
├── pipeline.pkl
└── README.md
```


