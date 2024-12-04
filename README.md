# Bankrupt Detection Model

This project predicts the likelihood of bankruptcy using financial metrics. The analysis involves exploratory data analysis (EDA), feature engineering, model building, and performance evaluation.

---

## Table of Contents
- [Introduction](#introduction)
- [Dataset Overview](#dataset-overview)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Top Correlated Features](#top-correlated-features)
- [Data Processing](#data-processing)
- [Model Building](#model-building)
- [Performance Evaluation](#performance-evaluation)
- [Model Comparison and Results](#model-comparison-and-results)
- [Limitations and Future Work](#limitations-and-future-work)
- [How to Run](#how-to-run)
- [Requirements](#requirements)
- [License](#license)

---

## Introduction
Bankruptcy prediction is crucial for risk mitigation and financial stability. This project develops machine learning models to classify companies as bankrupt or non-bankrupt using financial data.

---

## Dataset Overview
- **Class Imbalance:** 220 bankrupt cases, 6,599 non-bankrupt cases.
- **Clean Data:** No missing or duplicate values.
- **Features:** Financial ratios and metrics such as debt ratios, liabilities, and equity measures.

---

## Exploratory Data Analysis

### Target Distribution
The dataset is highly imbalanced, with bankrupt cases forming a minority class.

![Target Distribution](images/target_distribution.png)

### Correlation Heatmap
The heatmap reveals the correlation between features and the target variable.

![Correlation Heatmap](images/correlation_heatmap.png)

---

## Top Correlated Features

1. **Debt Ratio %**
   - Highly correlated with bankruptcy.
   - Skewed distribution with concentrated values.
   - ![Debt Ratio Pairplot](images/debt_ratio_pairplot.png)

2. **Current Liability to Assets**
   - Indicates liability proportion relative to assets.
   - Strongly associated with bankruptcy.
   - ![Current Liability to Assets Pairplot](images/current_liability_assets_pairplot.png)

3. **Borrowing Dependency**
   - Reflects reliance on borrowed funds.
   - Key differentiator for bankruptcy cases.
   - ![Borrowing Dependency Pairplot](images/borrowing_dependency_pairplot.png)

4. **Liability to Equity**
   - Measures leverage.
   - Displays notable clustering for bankrupt firms.
   - ![Liability to Equity Pairplot](images/liability_to_equity_pairplot.png)

5. **Total Expense to Assets**
   - Indicates asset efficiency in managing expenses.
   - Positively linked with bankruptcy.
   - ![Total Expense to Assets Pairplot](images/total_expense_assets_pairplot.png)

---

## Data Processing
1. **Class Balancing:** Used SMOTE to handle class imbalance.
2. **Feature Engineering:** Selected features with the highest correlation to the target.
3. **Data Splitting:** 80% training and 20% testing.

---

## Model Building
Implemented the following machine learning models:
- Decision Tree
- Random Forest
- Gradient Boosting (XGBoost)

---

## Performance Evaluation

### Confusion Matrices
The confusion matrices for the models provide insights into the classification results:

- **Random Forest**  
  ![Confusion Matrix Random Forest](images/confusion_matrix_rf.png)

- **Decision Tree**  
  ![Confusion Matrix Decision Tree](images/confusion_matrix_dt.png)

- **XGBoost**  
  ![Confusion Matrix XGBoost](images/confusion_matrix_xgb.png)

### Metrics
The following table summarizes the performance metrics for each model:

| Model               | Accuracy | Precision | Recall  | F1 Score | ROC AUC  |
|---------------------|----------|-----------|---------|----------|----------|
| Random Forest       | 0.7848   | 0.9619    | 0.5932  | 0.7338   | 0.9561   |
| Decision Tree       | 0.7746   | 0.9220    | 0.6000  | 0.7269   | 0.7746   |
| XGBoost             | 0.8326   | 0.9650    | 0.6902  | 0.8048   | 0.9647   |

---

## Model Comparison and Results

- **XGBoost** emerged as the best-performing model with:
  - Highest accuracy (83.26%)
  - Highest ROC-AUC (0.9647)
  - Balanced precision (0.965) and recall (0.6902)

- The confusion matrices reveal that XGBoost effectively reduces false negatives compared to other models.

---

## Limitations and Future Work

### Limitations
- Imbalanced data may affect minority class predictions.
- Limited interpretability of ensemble models like Gradient Boosting.

### Future Work
- Test on external datasets to validate generalizability.
- Explore additional financial features or macroeconomic indicators.

---

## How to Run

1. Clone the repository:
   ```bash
   git clone <repository-url>
