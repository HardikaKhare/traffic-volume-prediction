# Traffic Volume Prediction using Machine Learning

This project predicts traffic volume using historical traffic data from the Metro Interstate Traffic dataset.

## Dataset
The dataset contains hourly traffic data along with weather and time-related information.

## Features Used
- Hour of the day
- Day of the week
- Previous hour traffic (lag_1)

## Model
A Linear Regression model was trained using scikit-learn.

## Evaluation Metrics
The model performance was evaluated using:
- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)

Results:
- MAE ≈ 508
- RMSE ≈ 704

## Visualization
The predicted traffic values were compared with actual values to evaluate how well the model captures traffic patterns.

## Project Structure
Traffic_Prediction/
|
|--data/
|
|--models/
|
|--notebooks/
|  traffic_prediction_model.ipynb
|
|--README.md


## Future Improvements

- Add additional lag features (lag_2, lag_3, lag_6)
- Experiment with other models such as Random Forest and Gradient Boosting
- Build an API service to serve predictions
- Deploy the model as a simple web application
