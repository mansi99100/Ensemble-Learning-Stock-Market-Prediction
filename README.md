# 📈 Ensemble Learning Paradigm for Stock Market Prediction

A machine learning project that applies **stacking ensemble regression** to historical Reliance Industries stock data to predict closing prices and evaluate model performance using regression metrics, cross-validation, and visualizations.

## 📌 Overview

Stock market prediction involves analyzing historical market data to identify patterns and estimate future prices. This project explores an ensemble learning approach that combines multiple regression algorithms to generate stock price predictions.

The implementation uses a **StackingRegressor** with Decision Tree, Support Vector Regression (SVR), and Gradient Boosting as base learners. A secondary Gradient Boosting Regressor combines their predictions to produce the final output.

The project covers data preprocessing, feature scaling, model training, cross-validation, performance evaluation, and graphical analysis.

## 🎯 Project Objectives

- Develop a machine learning pipeline for stock closing price prediction.
- Combine multiple regression algorithms using stacking ensemble learning.
- Evaluate predictive performance using standard regression metrics.
- Assess model performance through 5-fold cross-validation.
- Explore classification metrics by converting continuous predictions into binary categories.

## 🔬 Research & Publication

The methodology and findings associated with this project were published at the **3rd International Conference on Advances in Computing, Communication and Information Technology (ICAICCIT), October 2025**.

## 📂 Dataset

The project uses historical Reliance Industries stock market data originally sourced from Kaggle.

| Attribute | Details |
|---|---|
| Dataset file | `reliance_data.csv` |
| Original records | 6,205 rows |
| Original columns | 15 |
| Historical period | January 1996 – December 2019 |
| Records after preprocessing | 2,356 complete rows |
| Target variable | `Close` |

### Features Used

The model uses the following market-related features:

- `Prev Close`
- `Open`
- `High`
- `Low`
- `Last`
- `VWAP`
- `Volume`
- `Turnover`
- `Trades`
- `Deliverable Volume`
- `%Deliverble`

Metadata columns such as `Date`, `Symbol`, and `Series` are excluded during preprocessing.

## 🧠 Methodology

### 1. Data Preprocessing
- Load historical stock data from the CSV file.
- Remove metadata columns not used as model features.
- Handle missing values by removing incomplete records.
- Standardize features using Scikit-learn's `StandardScaler`.

### 2. Stacking Ensemble Architecture

The model combines three base estimators with a final meta-estimator.

**Base learners:**

1. Decision Tree Regressor
2. Support Vector Regressor (SVR)
3. Gradient Boosting Regressor

**Meta-estimator:**

A Gradient Boosting Regressor learns from the base estimators' predictions to generate the final stock price estimate.

### 3. Cross-Validation

The pipeline uses **5-fold cross-validation** to examine model performance across multiple data splits using the R² score.

### 4. Model Evaluation

The notebook evaluates model performance using regression metrics and classification metrics derived from threshold-based categories.

## 📊 Evaluation Metrics

### Regression Metrics

| Metric | Purpose |
|---|---|
| MAE | Measures average absolute prediction error |
| MSE | Measures average squared prediction error |
| RMSE | Measures prediction error in the target variable's units |
| R² Score | Measures how well the model explains target variability |

### Classification Metrics

Continuous outputs are converted into categorical labels using a median-based threshold.

- Accuracy
- Precision
- Recall
- F1 Score

These metrics evaluate the resulting categories rather than the accuracy of continuous price forecasts.

## 🗂️ Project Structure

```text
Ensemble-Learning-Stock-Market-Prediction/
│
├── Stacking Regressor with graph (2).ipynb
├── reliance_data.csv
└── README.md
```

- **Jupyter Notebook:** Contains data preprocessing, model implementation, evaluation, and visualizations.
- **CSV Dataset:** Contains historical Reliance Industries stock market data.
- **README.md:** Documents the project, methodology, and setup instructions.

## ⚙️ Installation & Usage

### Prerequisites

- Python 3.9+
- Jupyter Notebook
- Basic familiarity with Python and machine learning

### 1. Clone the Repository

```bash
git clone https://github.com/mansi99100/Ensemble-Learning-Stock-Market-Prediction.git
cd Ensemble-Learning-Stock-Market-Prediction
```

### 2. Install Dependencies

```bash
pip install pandas numpy scikit-learn matplotlib jupyter
```

### 3. Launch Jupyter Notebook

```bash
jupyter notebook "Stacking Regressor with graph (2).ipynb"
```

### 4. Run the Notebook

Execute the notebook cells sequentially to load the dataset, preprocess the data, train the stacking ensemble, evaluate model performance, and generate visualizations.

## 🛠️ Technologies Used

- **Python** — Core programming language
- **Pandas** — Data manipulation and preprocessing
- **NumPy** — Numerical computations
- **Scikit-learn** — Machine learning models, feature scaling, and cross-validation
- **Matplotlib** — Data visualization
- **Jupyter Notebook** — Experimentation and implementation

## ⚠️ Limitations

- The dataset covers historical observations only through December 2019.
- Stock prices are influenced by market conditions and external factors not necessarily captured by the selected features.
- Cross-validation performance does not guarantee future predictive accuracy.
- Median-threshold classification metrics represent derived categories, not direct measures of price prediction accuracy.

**Disclaimer:** This project is intended for educational and research purposes. Its predictions should not be considered financial advice or a guarantee of future market performance.

## 👩‍💻 Author

**Mansi Rawat**

- GitHub: [@mansi99100](https://github.com/mansi99100)

---

*Exploring the application of ensemble learning techniques to historical stock market data.*
