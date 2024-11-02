# Demand Forecasting Project

This project aims to forecast weekly sales demand using time series analysis techniques.  The project employs both machine learning (RandomForestRegressor) and statistical modeling (Exponential Smoothing and Auto ARIMA) approaches to predict demand, offering a comparative analysis of different methods.  A Streamlit web application is developed to provide an interactive interface for generating predictions.


## Table of Contents

* [Data](#data)
* [Preprocessing](#preprocessing)
* [Model Building](#model-building)
    * [Random Forest Regressor](#random-forest-regressor)
    * [Time Series Models](#time-series-models)
        * [Auto ARIMA](#auto-arima)
        * [Exponential Smoothing](#exponential-smoothing)
* [Model Evaluation](#model-evaluation)
* [Streamlit App](#streamlit-app)
* [Deployment](#deployment)
* [Usage](#usage)
* [Project Structure](#project-structure)
* [Contributing](#contributing)
* [License](#license)


## Data

The project uses a dataset containing historical sales data, along with relevant features such as store information, holidays, and promotional markdowns.  The dataset is cleaned and preprocessed to handle missing values and inconsistencies. The original dataset is located at [link to original data source].  A cleaned and preprocessed version is included in this repository (`data_cleaned.csv`).


## Preprocessing

The preprocessing steps include:

* **Data Cleaning:** Handling missing values and outliers.
* **Feature Engineering:** Creating new features, such as the month of the year.
* **Data Encoding:** Converting categorical variables (e.g., store type, holidays) into numerical representations.
* **Data Transformation:** Applying transformations like differencing or taking the logarithm of the target variable ('Weekly_Sales') to improve stationarity for time series models.



## Model Building

The project explores different models for demand forecasting:

### Random Forest Regressor

A Random Forest Regressor model is trained on the preprocessed data using features like store information, holidays, and markdowns.  Feature importance analysis is conducted to identify the most influential factors driving sales.

### Time Series Models

Two time series models are developed:

#### Auto ARIMA

An Auto ARIMA model is used to capture the autocorrelations and seasonality present in the time series data. The `pmdarima` library is used to automatically determine optimal model parameters (p, d, q) and seasonal components (P, D, Q, m).

#### Exponential Smoothing

An Exponential Smoothing model with additive trend and seasonality is also implemented, particularly suitable if the data exhibits a trend and seasonality.


## Model Evaluation

The models are evaluated using metrics such as Weighted Mean Absolute Error (WMAE) for the RandomForestRegressor and Mean Absolute Error (MAE) or other appropriate metrics for the time series models.
