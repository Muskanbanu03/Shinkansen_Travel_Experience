# 🚄 Shinkansen Bullet Train — Passenger Experience Prediction

**Hackathon Project — Great Lakes Institute of Management**

## Overview
Machine learning project to predict whether a passenger was satisfied with their overall travel experience on Japan's Shinkansen Bullet Train, using both on-time performance data and post-journey survey feedback.

## Objective
Determine which travel and service parameters most strongly influence passenger satisfaction, to help identify actionable improvement areas.

## Dataset
- **Travel data**: on-time performance and passenger details (`Traveldata_train.csv`)
- **Survey data**: post-journey feedback across multiple service parameters (`Surveydata_train.csv`)
- **Target variable**: `Overall_Experience` (1 = satisfied, 0 = not satisfied)
- **Size**: 100,000+ passenger records (merged on passenger ID)

## Workflow

### 1. Data Preparation
- Merged travel and survey datasets on passenger `ID`
- Analyzed missing value patterns across both datasets

### 2. Feature Engineering
- Converted delay columns (minutes → hours) for interpretability
- Dropped low-value columns (e.g., `Seat_Class`)

### 3. Missing Value Imputation
- Mode imputation for categorical features
- Mean imputation for `Age` (normally distributed)
- Median imputation for delay columns (right-skewed)

### 4. Encoding & Scaling
- One-hot encoding for categorical variables
- StandardScaler applied to numeric features

### 5. Class Imbalance Handling
- Compared **undersampling** and **SMOTE oversampling** against the original class distribution

### 6. Model Comparison
Benchmarked across original, undersampled, and oversampled data:
- Logistic Regression, GaussianNB, KNN, LDA, Decision Tree, Bagging, XGBoost

### 7. Hyperparameter Tuning
Tuned via RandomizedSearchCV: XGBoost, Random Forest, Decision Tree, Bagging, Gradient Boosting, KNN

### 8. Ensemble Modeling
Built a stacking ensemble combining Bagging and Random Forest, with XGBoost as the final estimator

## Results
- **Test accuracy:** 92.9% *(verify against your saved notebook output before publishing)*
- Ranked among top performers in the hackathon cohort

## Tools & Libraries
Python, Pandas, NumPy, Scikit-learn, XGBoost, Imbalanced-learn (SMOTE)
