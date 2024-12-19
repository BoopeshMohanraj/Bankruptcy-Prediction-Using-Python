# Bankruptcy Prediction Model

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
- [Socialization and Distribution](#socialization-and-distribution)
- [Value and Next Steps](#value-and-next-steps)
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

![Target Distribution]![image](https://github.com/user-attachments/assets/9a2d8778-059a-4356-9060-e1753d1e5326)


### Correlation Heatmap
The heatmap reveals the correlation between features and the target variable.

![Correlation Heatmap]![image](https://github.com/user-attachments/assets/f2dbd73c-b62f-4690-bb66-5562b2ec7af6)


---

## Top Correlated Features

### Exploration of Top 10 Most Correlated Features to Target
1. **Debt Ratio %**
   - Highly correlated with bankruptcy.
   - Skewed distribution with concentrated values.
   - ![Debt Ratio Pairplot]![image](https://github.com/user-attachments/assets/fb8eca24-6200-4769-860e-083f7f6891cf)
   - Distribution by target class
   - ![image](https://github.com/user-attachments/assets/6c585eb6-08ef-4740-a985-db7115e79e93)

2. **Current Liability to Assets**
   - Indicates liability proportion relative to assets.
   - Strongly associated with bankruptcy.
   - ![Current Liability to Assets Pairplot]![image](https://github.com/user-attachments/assets/58a016fc-df5c-4af7-8a95-01b18552042e)
   - Distribution by target class
   - ![image](https://github.com/user-attachments/assets/72f6e941-5271-455d-851b-53bf22208f49)

3. **Borrowing Dependency**
   - Reflects reliance on borrowed funds.
   - Key differentiator for bankruptcy cases.
   - ![Borrowing Dependency Pairplot](![image](https://github.com/user-attachments/assets/1d7d7736-30d6-442f-857e-2fba780523da)
   - Distribution by target class
   - ![image](https://github.com/user-attachments/assets/1b89da0d-e6dc-4cf8-b5ce-2263828d9b3a)

4. **Current Liability to Current Assets**
   - Measures the ratio of current liabilities to current assets.
   - Affects the financial health of firms.
   - ![Current Liability to Current Assets Pairplot]![image](https://github.com/user-attachments/assets/bce10bbf-fdd5-446f-b586-eb725f829595)
   - Distribution by target class
   - ![image](https://github.com/user-attachments/assets/8ffd13d6-b33c-4cfe-b171-4abf68c17b8e)

5. **Liability to Equity**
   - Measures leverage.
   - Displays notable clustering for bankrupt firms.
   - ![Liability to Equity Pairplot]![image](https://github.com/user-attachments/assets/045712df-1deb-416b-a737-1784e6e48a09)
   - Distribution by target class
   - ![image](https://github.com/user-attachments/assets/8f060204-6f41-4d60-8a30-5a1402d0b264)

6. **Current Liabilities to Equity**
   - Indicates the proportion of current liabilities compared to equity.
   - A significant predictor of financial instability.
   - ![Current Liabilities to Equity Pairplot]![image](https://github.com/user-attachments/assets/11a51f53-b0bd-4032-b616-65a9ae6f4d69)
   - Distribution by target class
![image](https://github.com/user-attachments/assets/6a7350fa-60cf-4692-a288-65b3e0bb00c9)

7. **Current Liability to Equity**
   - Similar to the previous feature, focused specifically on equity utilization.
   - ![Current Liability to Equity Pairplot]![image](https://github.com/user-attachments/assets/8f1b7dee-ac11-4fda-a447-dc86ab5c8b0e)
   - Distribution by target class
![image](https://github.com/user-attachments/assets/92300d55-c27c-4a0c-a645-cad4b2345674)


8. **Liability-Assets Flag**
   - Binary feature indicating whether liabilities exceed assets.
   - ![Liability Assets Flag Pairplot]![image](https://github.com/user-attachments/assets/7b02c96c-628d-4782-9e3a-010bb57cf700)
Distribution by target class
![image](https://github.com/user-attachments/assets/b237330b-dff3-4095-a1c9-816a52989f30)

9. **Total Expense to Assets**
   - Indicates asset efficiency in managing expenses.
   - Positively linked with bankruptcy.
   - ![Total Expense to Assets Pairplot]![image](https://github.com/user-attachments/assets/4d5b78ad-b043-4244-acba-4de20253f8da)
   - Distribution by target class![image](https://github.com/user-attachments/assets/8f64b0d0-4609-4423-88f7-206fa2f57c7a)

10. **Equity to Long-term Liability**
    - Captures the ratio of equity to long-term liabilities.
    - Highlights a company's ability to manage long-term debt.
    - ![Equity to Long-term Liability Pairplot]![image](https://github.com/user-attachments/assets/18d052c8-25e6-44eb-9b22-585a7646d892)
    - Distribution by target class
    - ![image](https://github.com/user-attachments/assets/0bc7e442-140c-4c07-b98e-5fa8b028e236)

---

## Data Processing
1. **Class Balancing:** Used SMOTE to handle class imbalance.![image](https://github.com/user-attachments/assets/7f5291b5-1a7f-4351-a7dc-a82dd86be79d)


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

- **Decision Tree**  

- **XGBoost**  

### Metrics
The following table summarizes the performance metrics for each model:

![image](https://github.com/user-attachments/assets/c84bf8be-91d2-4c4c-88c0-3a470ce2a75f)
| Model               | Accuracy | Precision | Recall  | F1 Score | ROC AUC  |
|---------------------|----------|-----------|---------|----------|----------|
| Random Forest       | 0.7848   | 0.9619    | 0.5932  | 0.7338   | 0.9561   |
| Decision Tree       | 0.7746   | 0.9220    | 0.6000  | 0.7269   | 0.7746   |
| XGBoost             | 0.8326   | 0.9650    | 0.6902  | 0.8048   | 0.9647   |

![image](https://github.com/user-attachments/assets/c525c303-ef8e-413a-9138-d06d7c716452)


---

## Model Comparison and Results

- **XGBoost** emerged as the best-performing model with:
  - Highest accuracy (83.26%)
  - Highest ROC-AUC (0.9647)
  - Balanced precision (0.965) and recall (0.6902)
- Chose to prioritize both accuracy and recall as accuracy can be misleading in imbalanced datasets, but recall shows the true positive rate.

![image](https://github.com/user-attachments/assets/03cd725f-e8b2-405c-a124-54916fe1c27a)


### Feature Importance
Feature importance analysis highlighted:
- Financial ratios
- Cash flow indicators
- Profitability metrics

![Feature Importance]

---

## Socialization and Distribution
Sharing results with stakeholders through:
- **Monthly Updates:** Dashboards displaying predictions and key drivers for a company’s financial operations.
- **Web Application:** Broader distribution for quick access to predictions and insights.

---

## Value and Next Steps

### Value
- **Identify Risks Early:** Predict bankruptcy beforehand to prevent financial collapse.

### Next Steps
- Expand functionality to businesses under varied business regulations.
- Improve the model by selecting critical parameters to enhance predictive accuracy.
- Conduct hyper-parameter tuning to optimize recall.
- Collect additional data from recent financial periods to enhance applicability.

---

## How to Run

1. Clone the repository:
   ```bash
   git clone <repository-url>
