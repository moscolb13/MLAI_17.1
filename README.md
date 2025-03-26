# ML/AI Assignment 17.1

## Overview

This project explores classification models using real-world marketing campaign data from a bank. The primary goal is to predict whether a client will subscribe to a term deposit (`yes` or `no`) following a direct marketing call. The task applies multiple machine learning models to test agaisnst a baseline.

---

## Dataset

The dataset comes from 17 separate marketing campaigns conducted between 2008–2010, totaling 79,354 contacts. It includes both numerical and categorical features related to client demographics, bank records, and campaign details.

File used: `bank-additional-full.csv`  
Target variable: `y` – whether the client subscribed (`yes`/`no`)

## Methods

### 1. **Preprocessing**
- Converted categorical variables using one-hot encoding
- Mapped binary `yes`/`no` values to 1/0
- Standardized numerical features for applicable models

### 2. **Baseline Model**
- `DummyClassifier` predicting the most frequent class (always “no”)
- Established base accuracy and ROC AUC to beat (0.5)

### 3. **Classification Models**
- **Logistic Regression** 
- **K-Nearest Neighbors**
- **Decision Tree**
- **Support Vector Machine**

Each model was trained on 70% of the data and tested on 30%, using stratified sampling.

### 4. **Model Evaluation**
- Accuracy
- Precision, Recall, F1-score (focus on minority class `y=1`)
- ROC AUC Score
- Confusion Matrix

### 5. **Model Improvements**
- Dropped low-value features (`day_of_week`)
- Adjusted classification threshold for Logistic Regression to improve recall


##  Key Results

| Model                     | Accuracy | F1 (yes) | ROC AUC |
|--------------------------|----------|----------|----------|
| Baseline (dummy)         | 89%      | 0.00     | 0.50      |
| Logistic Regression      | **91%**  | 0.51     | **0.936** |
| Logistic (0.4 threshold) | 91%      | **0.57** | 0.936     |
| KNN (k=5)                | 90%      | 0.43     | 0.82      |
| Decision Tree            | 89%      | 0.51     | 0.73      |
| SVM (RBF)                | 91%      | 0.48     | 0.929     |

Logistic Regression with a threshold of 0.4 offered the best performance.



## Conclusion

This project demonstrates how different classification algorithms behave with imbalanced, real-world marketing data. Logistic regression outperformed more complex models , and thoughtful feature engineering (like dropping `day_of_week`) simplified the model without sacrificing performance.
