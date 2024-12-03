# Bankruptcy-Prediction-Using-Python

# Bankrupt Detection Model

This project focuses on building a predictive model to detect the likelihood of bankruptcy for companies using financial metrics. It includes data exploration, feature engineering, model building, and performance evaluation.

## Table of Contents
- [Introduction](#introduction)
- [Dataset Overview](#dataset-overview)
- [Exploratory Data Analysis](#exploratory-data-analysis) 
- [Data Processing](#data-processing)
- [Model Building](#model-building)
- [Performance Evaluation](#performance-evaluation)
- [Model Comparison and Selection](#model-comparison-and-selection)
- [How to Run](#how-to-run)
- [Results](#results)

## Introduction
This project analyzes financial indicators to predict bankruptcy. The goal is to develop a robust model to classify companies as bankrupt or non-bankrupt using machine learning techniques.

## Dataset Overview
The dataset contains financial data, with columns including metrics like debt ratio, liability to assets, and other indicators. Key highlights:
- No null or duplicate values
- The target distribution shows a class imbalance: 220 bankrupt cases vs. 6,599 non-bankrupt cases

## Exploratory Data Analysis
We explored various financial ratios and their correlations with the target. Key features:
- Debt Ratio %: Majorly concentrated in a specific range
- Current Liability to Assets: Skewed with a tight range
- Borrowing Dependency: A few distinct values dominate
- Liability-Assets Flag: Binary feature (0 or 1)

## Data Processing
The processing steps include:
1. Cleaning column names
2. Handling class imbalance through techniques like SMOTE
3. Splitting the dataset into training and testing sets

## Model Building
Various machine learning algorithms were implemented to classify the data. Feature engineering and hyperparameter tuning were applied to optimize performance.

## Performance Evaluation
Models were evaluated using metrics such as:
- Accuracy
- Precision 
- Recall
- F1 Score
- ROC-AUC Curve
# Distribution

# Cut the window in 2 parts
f, (ax_box, ax_hist) = plt.subplots(2, sharex=True, gridspec_kw={"height_ratios": (.15, .85)})
sns.set(style="darkgrid")

# Add a graph in each part
sns.boxplot(df["Debt ratio %"], orient = 'h', ax=ax_box)
sns.distplot(df["Debt ratio %"], ax=ax_hist)
ax_hist.set(xlabel='Debt Ratio %')
plt.show()
## Model Comparison and Selection
A comparative analysis was performed across models to identify the best-performing algorithm.

## How to Run
1. Clone this repository:
```bash
git clone <repository-url>
Install the required packages:
bash


pip install -r requirements.txt
```
Run the Jupyter Notebook:

jupyter notebook Project1.ipynb
### Results
The final model achieved significant accuracy and balanced performance across all metrics, successfully identifying rare bankruptcy cases.

License
This project is licensed under the MIT License. See the LICENSE file for details.
