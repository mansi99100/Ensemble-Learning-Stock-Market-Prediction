# Ensemble Learning Paradigm for Stock Market Predictions

## Overview

This repository features a machine learning pipeline for predicting stock market closing prices using an advanced ensemble learning approach. Specifically focused on Reliance Industries historical data, the project implements a `StackingRegressor` to combine the predictive strengths of multiple algorithms, significantly enhancing overall forecasting stability and accuracy.

The core implementation, data pipeline, and evaluation visualizations are housed entirely in the `Stacking Regressor with graph (2).ipynb` notebook.

## Research & Publication

The methodology and findings underlying this codebase were peer-reviewed and published at the **3rd International Conference on Advances in Computing, Communication and Information Technology (ICAICCIT)** in October 2025.

## Dataset

The model is trained on the Reliance Industries dataset (`reliance_data.csv`), originally sourced from Kaggle.

* **Timeframe:** January 1996 to December 2019.
* **Shape:** 6,205 original rows and 15 columns (filtered to 2,356 complete rows during preprocessing to ensure high data quality).
* **Features Used:** `Prev Close`, `Open`, `High`, `Low`, `Last`, `VWAP`, `Volume`, `Turnover`, `Trades`, `Deliverable Volume`, `%Deliverble`.
* **Target Variable:** `Close` (Closing Price).

*(Note: Metadata columns such as `Date`, `Symbol`, and `Series` are explicitly dropped during the preprocessing stage).*

## Project Structure

* `Stacking Regressor with graph (2).ipynb`: The primary Jupyter Notebook containing the end-to-end pipeline (data ingestion, preprocessing, modeling, evaluation, and visualization).
* `reliance_data.csv`: The raw historical stock data file.

## Methodology

1. **Data Preprocessing:** Cleans raw stock data by dropping non-numeric columns, dropping missing values (`NaN`), and standardizing features using Scikit-Learn's `StandardScaler`.
2. **Stacking Ensemble Architecture:** Integrates three base estimators to capture varying data patterns:
* Decision Tree Regressor
* Support Vector Regressor (SVR)
* Gradient Boosting Regressor


3. **Meta-Estimator:** A secondary Gradient Boosting Regressor acts as the final meta-estimator, refining the outputs of the base models into the ultimate prediction.
4. **Cross-Validation:** Uses 5-fold cross-validation to validate the model's R² score across different data splits, preventing overfitting.

## Evaluation Metrics

The pipeline assesses performance across dual domains:

* **Regression Metrics:** Mean Absolute Error (MAE), Mean Squared Error (MSE), Root Mean Squared Error (RMSE), and R² Score.
* **Classification Metrics:** Converts continuous regression outputs into categorical labels (based on a median threshold) to calculate Accuracy, Precision, Recall, and F1 Score.

## Installation & Usage

1. Clone the repository:
```bash
git clone https://github.com/yourusername/stock-market-ensemble.git
cd stock-market-ensemble

```


2. Ensure you have the required dependencies installed:
```bash
pip install pandas numpy scikit-learn matplotlib

```


3. Open the Jupyter Notebook:
```bash
jupyter notebook "Stacking Regressor with graph (2).ipynb"

```


4. Run the cells sequentially to preprocess the data, train the ensemble model, and generate the cross-validation performance graphs.
