# Credit Risk Prediction

An end-to-end machine learning application for predicting credit/loan default risk using applicant financial and loan information.

The project combines machine learning, explainable AI, and a FastAPI backend with a web-based frontend to provide real-time credit risk predictions.

---

## Project Overview

Credit risk assessment is an important task in financial services. The goal of this project is to build a machine learning system that estimates the probability of loan default based on an applicant's financial and loan-related information.

The project covers the complete machine learning workflow:

- Exploratory Data Analysis
- Data validation and cleaning
- Feature preprocessing
- Handling class imbalance
- Logistic Regression baseline
- XGBoost classification
- Hyperparameter tuning
- Model evaluation
- Classification threshold optimization
- Probability calibration
- SHAP-based model interpretation
- FastAPI deployment
- Web-based prediction interface

---

## Features

- Credit default risk prediction
- Default probability estimation
- High Risk / Low Risk classification
- XGBoost-based machine learning model
- Handling of imbalanced classes
- Hyperparameter optimization
- Probability calibration
- Explainable AI using SHAP
- REST API using FastAPI
- Web-based frontend
- Deployment configuration for Render

---
## Dataset

The dataset contains information related to loan applicants, including:

Age
Income
Home ownership
Employment length
Loan intent
Loan grade
Loan amount
Loan interest rate
Loan percentage of income
Previous default history
Credit history length

 The target variable is:

loan_status

where the model predicts whether an applicant belongs to the default-risk class.
---

## Machine Learning Models
### Logistic Regression

Logistic Regression was implemented as a baseline model.

The preprocessing pipeline includes:

Missing-value imputation
Standard scaling for numerical features
One-hot encoding for categorical features
Balanced class weights

### XGBoost
XGBoost was used as the main tree-based classification approach.
The preprocessing pipeline includes:

Missing-value imputation
One-hot encoding of categorical variables
Class imbalance handling
Hyperparameter optimization

RandomizedSearchCV was used for hyperparameter tuning.
---

### Model Evaluation

The models were evaluated using:

Accuracy
Precision
Recall
F1 Score
ROC-AUC
Confusion Matrix
Precision-Recall Curve

The cross-validation results from the notebook showed:

| Model               | ROC-AUC | Accuracy | Precision | Recall |    F1 |
| ------------------- | ------: | -------: | --------: | -----: | ----: |
| Logistic Regression |   0.871 |    0.812 |     0.545 |  0.778 | 0.641 |
| XGBoost             |   0.939 |    0.909 |     0.791 |  0.786 | 0.788 |


These values are from the 5-fold cross-validation experiment in the project notebook.

### Explainable AI

SHAP (SHapley Additive exPlanations) was used to interpret the XGBoost model.

The project includes:

### Global Explanation

Identifies which features have the greatest influence on model predictions.

### Local Explanation

Explains why a particular applicant received a particular prediction.

This helps make the machine learning model more interpretable.

### FastAPI Application

The trained model is served through a FastAPI backend.

The main prediction endpoint is:

POST /predict

The API accepts applicant information and returns:

{
    "default_probability": 0.XX,
    "default_prediction": 0,
    "threshold": 0.XX,
    "Result": "Low Risk"
}

Possible results are:

High Risk
Low Risk

### Input Features

The prediction API accepts:
```text
person_age
person_income
person_home_ownership
person_emp_length
loan_intent
loan_grade
loan_amnt
loan_int_rate
loan_percent_income
cb_person_default_on_file
cb_person_cred_hist_length


### Project Structure
```text
credit-risk-prediction/
│
├── static/
│   ├── index.html
│   ├── script.js
│   └── style.css
│
├── Credit_Risk.ipynb
├── credit_risk_dataset.csv
├── credit_risk_model.pkl
├── best_threshold.pkl
├── main.py
├── requirements.txt
├── runtime.txt
├── render.yaml
├── README.md
└── .gitignore


Machine Learning Pipeline

The project follows this workflow:
Raw Dataset
     ↓
Exploratory Data Analysis
     ↓
Data Cleaning & Validation
     ↓
Train / Test Split
     ↓
Class Imbalance Handling
     ↓
Feature Preprocessing
     ↓
Logistic Regression Baseline
     ↓
XGBoost Model
     ↓
Hyperparameter Tuning
     ↓
Model Evaluation
     ↓
Probability Calibration
     ↓
Threshold Optimization
     ↓
Saved Model
     ↓
FastAPI
     ↓
Web Application

### Future Improvements

Possible improvements include:

Adding stronger data validation
Improving probability calibration
Adding model monitoring
Adding automated testing
Adding authentication for the API
Adding database integration
Adding more detailed applicant-level explanations
Improving the frontend user experience

