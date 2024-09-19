# Interpretable ML: Linear Regression, Logistic Regression and Generalized Additive Model (GAM)

# Telecom Customer Churn Prediction

This repository contains an analysis of telecom customer churn using various machine learning models, including Linear Regression, Logistic Regression, and Generalized Additive Models (GAM). The goal is to predict customer churn and interpret the key drivers influencing customer churn behavior.

## Table of Contents

- [Overview](#overview)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Models and Performance](#models-and-performance)
- [Interpretation](#interpretation)
- [Results](#results)
- [Conclusion](#conclusion)
- [References](#references)

## Overview

Customer churn is a critical problem in the telecom industry. Understanding which customers are likely to leave and the reasons for their churn can significantly improve retention efforts. This project applies several interpretable machine learning models to identify key drivers of churn and provide actionable insights.

### Dataset

The dataset used for this project is available on Kaggle: [Telco Customer Churn Dataset](https://www.kaggle.com/blastchar/telco-customer-churn/code).

The dataset contains customer information, such as:

- **Demographic features** (e.g., gender, senior citizen status, partner status)
- **Service-related features** (e.g., internet service, tech support, contract type)
- **Account information** (e.g., tenure, monthly charges, total charges)

The target variable is `Churn`, where `1` represents a customer who has churned and `0` represents a customer who has stayed.

## Project Structure

```
|-- telecom_churn_analysis.ipynb    # Main notebook for running models
|-- README.md                    # Project documentation
|-- data/                        # Folder for dataset (to be added)
```

## Installation

To run this project go to the main notebook and simply open them in Google Colab using the provided link. 

## Models and Performance

The following models were implemented and evaluated:

### 1. **Linear Regression**
- **MSE**: 0.14
- **R² Score**: 0.25

Linear Regression is used to understand the linear relationships between features and churn, even though it is not typically appropriate for binary classification problems.

### 2. **Logistic Regression**
- **Accuracy**: 79.5%
- **AUC-ROC**: 0.84
- **Precision (Churn)**: 0.60
- **Recall (Churn)**: 0.53

Logistic Regression provides interpretable odds ratios for each feature, indicating the impact of each feature on the likelihood of churn.

### 3. **Generalized Additive Model (GAM)**
- **Accuracy**: 79.2%
- **AUC-ROC**: 0.85
- **Precision (Churn)**: 0.60
- **Recall (Churn)**: 0.51

GAMs capture non-linear relationships between customer features and churn, providing more flexible interpretations than logistic regression.

## Interpretation

- **Odds Ratios (Logistic Regression)**: Features like `tenure`, `contract type`, and `monthly charges` significantly affect churn.
- **Partial Dependence (GAM)**: Non-linear relationships are observed for features such as `tenure`, where customers with mid-range tenure have a higher probability of churn.

## Results

- **Linear Regression**: Low interpretability for binary classification. R² score is low.
- **Logistic Regression**: Provides a good balance of performance and interpretability, with decent accuracy and a high AUC-ROC score.
- **GAM**: Captures complex, non-linear relationships, slightly improving AUC-ROC but is more complex and harder to interpret.

## Conclusion

For the telecom company, **Logistic Regression** provides a good balance between interpretability and performance. While GAM slightly outperforms in some cases, its complexity might not justify the marginal improvement over Logistic Regression. For practical purposes, **Logistic Regression** with its interpretable coefficients (odds ratios) is recommended for churn prediction.

## References

- [Telco Customer Churn Dataset](https://www.kaggle.com/blastchar/telco-customer-churn/code)
- [Code reference](https://github.com/AIPI-590-XAI/Duke-AI-XAI/tree/main)