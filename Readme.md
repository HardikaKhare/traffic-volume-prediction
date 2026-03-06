# Traffic Volume Prediction using Machine Learning

## Overview

This project predicts hourly traffic volume using historical traffic and weather data.
The goal is to build a regression model that can estimate traffic volume based on time-based patterns and previous traffic values.

The project demonstrates a complete machine learning workflow including data preprocessing, feature engineering, model training, evaluation, and comparison.

---

## Dataset

The dataset used is the **Metro Interstate Traffic Volume dataset**, which contains hourly traffic data recorded on an interstate highway.

Features in the dataset include:

* Date and time of observation
* Weather conditions
* Temperature
* Rain and snow levels
* Cloud coverage
* Traffic volume

For this project, the focus was placed on **time-based patterns in traffic flow**.

---

## Feature Engineering

Several time-series features were created to help the model capture temporal patterns.

### Time-based Features

* **hour** – hour of the day extracted from the datetime column
* **day_of_week** – day index representing weekday/weekend behavior

### Lag Features

Lag features were created to incorporate past traffic values into the model.

* **lag_1** – traffic volume from 1 hour ago
* **lag_2** – traffic volume from 2 hours ago
* **lag_6** – traffic volume from 6 hours ago
* **lag_12** – traffic volume from 12 hours ago
* **lag_24** – traffic volume from the same hour on the previous day

These features allow the model to learn **short-term and daily traffic patterns**.

---

## Train-Test Split

Since this is **time-series data**, the dataset was split chronologically.

* Training data: earlier observations
* Test data: later observations

Shuffling was disabled to prevent **data leakage from future observations**.

---

## Models Used

Two regression models were trained and compared.

### Linear Regression

A simple baseline model used to establish a performance benchmark.

Advantages:

* Fast
* Interpretable
* Good starting point for regression problems

### Random Forest Regressor

A tree-based ensemble model capable of capturing nonlinear relationships between features.

Random Forest builds multiple decision trees and averages their predictions to improve performance and reduce overfitting.

Model implemented using:

* Scikit-learn RandomForestRegressor

---

## Evaluation Metrics

Model performance was evaluated using:

### Mean Absolute Error (MAE)

MAE measures the average absolute difference between predicted and actual traffic volume.

Interpretation:

* MAE = average prediction error in vehicles

### Root Mean Squared Error (RMSE)

RMSE penalizes larger prediction errors more strongly due to the squared error term.

This metric helps detect models that occasionally make large mistakes.

---

## Results

| Model             | MAE                | RMSE               |
| ----------------- | ------------------ | ------------------ |
| Linear Regression | ~445               | ~590               |
| Random Forest     | ~156               | ~ 251              |

The models were able to capture major traffic trends using lag-based temporal features.

---

## Visualization

Predicted traffic values were compared with actual traffic values using line plots to visually evaluate how well the models follow real traffic patterns.

These plots help assess how closely the model predictions track actual traffic fluctuations over time.

---

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Scikit-learn
* Jupyter Notebook

---

## Project Structure

Traffic_Prediction
│
├── data
│   └── Metro_Interstate_Traffic_Volume.csv
│
├── models
│   └── traffic_model.pkl
│
├── notebooks
│   └── traffic_prediction_model.ipynb
│
├── README.md
└── .gitignore

---

## Future Improvements

Possible improvements for this project include:

* Incorporating weather-related features into the model
* Testing additional models such as Gradient Boosting or XGBoost
* Performing hyperparameter tuning
* Adding weekly lag features (lag_168)
* Deploying the model using an API for real-time traffic prediction