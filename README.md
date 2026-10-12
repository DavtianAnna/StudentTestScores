# 🎓 Predicting Student Test Scores — Kaggle Playground Series S6E1

This repository contains my Machine Learning solution for the [Kaggle Playground Series — Predicting Student Test Scores](https://www.kaggle.com/competitions/playground-series-s6e1) competition.

The goal is to predict students' final exam scores (`exam_score`) based on various academic, behavioral, and environmental features. This is a **regression task** evaluated using **Root Mean Squared Error (RMSE)**.

## 📁 Project Structure

```text
project-root/
├── Task.ipynb                # Main notebook with the ML workflow
├── train.csv                 # Training dataset
├── test.csv                  # Test dataset
├── sample_submission.csv     # Kaggle submission template
├── submission1.csv           # SGDRegressor predictions
├── submission2.csv           # XGBRegressor predictions
└── README.md                 # Project documentation
```

## 💻 Technologies Used

- **Language:** Python 3.x
- **Environment:** Jupyter Notebook
- **Platform:** Kaggle

## 📦 Libraries

- **pandas** — Data loading and manipulation
- **NumPy** — Numerical computations
- **Matplotlib & Seaborn** — Data visualization
- **scikit-learn** — Data preprocessing, pipelines, model training, and hyperparameter tuning
- **XGBoost** — Gradient boosting regression

### Main Tools

- `LabelEncoder` — Encoding categorical labels
- `StandardScaler` — Feature standardization
- `Pipeline` — Combining preprocessing and model training
- `SGDRegressor` — Linear regression trained using stochastic gradient descent
- `XGBRegressor` — Gradient boosting regression model
- `GridSearchCV` — Hyperparameter tuning using cross-validation

## 📊 Dataset Description

The project uses the dataset provided by the [Kaggle Playground Series S6E1 competition](https://www.kaggle.com/competitions/playground-series-s6e1).

- **`train.csv`** — Training data containing student features and the target variable, `exam_score`.
- **`test.csv`** — Test data containing student features without the target variable.
- **`sample_submission.csv`** — Template specifying the required submission format.

## 🔁 Machine Learning Workflow

### 1. Data Loading and Preprocessing

- Loaded the training and test datasets using pandas.
- Identified and processed categorical features, including `gender`, `course`, `sleep_quality`, `internet_access`, `study_method`, `facility_rating`, and `exam_difficulty`.
- Applied categorical encoding using `LabelEncoder`.
- Removed the `id` column where appropriate.
- Prepared the datasets for model training and prediction.

### 2. Model Training and Hyperparameter Tuning

Two regression models were implemented and tuned using `GridSearchCV`.

| Model | Approach | Output File |
|---|---|---|
| `SGDRegressor` | `StandardScaler` + `Pipeline` + `GridSearchCV` | `submission1.csv` |
| `XGBRegressor` | `Pipeline` + `GridSearchCV` | `submission2.csv` |

**SGDRegressor**

A linear regression model trained using stochastic gradient descent. `StandardScaler` was used to standardize features, and `GridSearchCV` was applied to search for suitable hyperparameters.

**XGBRegressor**

A gradient boosting regression model that builds an ensemble of decision trees to capture relationships between features and the target variable. `GridSearchCV` was used to tune model hyperparameters.

### 3. Prediction and Submission

After training and hyperparameter tuning, predictions were generated for the test dataset and saved as CSV files.

- **`submission1.csv`** — Predictions from the tuned `SGDRegressor`.
- **`submission2.csv`** — Predictions from the tuned `XGBRegressor`.

Both files are intended to follow the submission format required by Kaggle.

## ⚙️ Installation and Usage

### 1. Clone the Repository

```bash
git clone https://github.com/DavtianAnna/StudentTestScores.git
cd StudentTestScores
```

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

