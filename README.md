# Credit Risk Prediction Project

## Overview
This project aims to predict the likelihood of loan default using borrower and loan characteristics. By utilizing machine learning models, the goal is to identify high-risk applicants and support better lending decisions.

## Objectives
- Analyze factors that contribute to loan default risk.
- Build predictive models to classify borrowers as default or non-default.
- Evaluate model performance and select the best model for deployment.
- Provide insights into key features influencing default risk.

## Dataset
- Source: [Kaggle Credit Risk Dataset](https://www.kaggle.com/datasets/laotse/credit-risk-dataset)
- Contains various features including:
    - Age
    - Income
    - Loan Amount
    - Previous Defaults
    - Loan Intent
    - Loan Grade
    - And more...

## Exploratory Data Analysis (EDA)
### Key questions addressed:
1. What is the overall default rate?
2. How does certain factors correlate with default risk?
3. Are there any differences in risk across loan purposes?
4. How does credit history affect default risk probability?

### Key Insights:
- Borrowers with higher loan-to-income ratios are at a significantly higher risk of default, especially if they have a history of prior default.
- Loan grade is a strong predictor of default risk, with lower grades (e.g., G and F) being associated with higher default rates.
- Borrowers with prior default history are more likely to default again.
- While income alone is not a strong predictor of default risk, it is important to consider it in conjunction with other factors such as loan amount and loan-to-income ratio for a more comprehensive assessment of default risk.

## Feature Engineering
- Added new features:
    - high_loan_burden: Indicates if loan_percent_income is greater than 0.5.
    - age_group: Categorizes ages into groups (e.g., Young, Middle-aged, Senior).
- Encoded categorical variables using one-hot encoding:
    - `person_home_ownership`
    - `age_group`
    - `loan_intent`
    - `loan_grade`
    - `cb_person_default_on_file`

## Machine Learning Modeling
### Models Used:
1. Logistic Regression
2. Random Forest
3. XGBoost

### Model Evaluation Metrics:
- Accuracy
- Precision
- Recall
- F1 Score
- ROC AUC Score

### Model Performance:
| Model              | Accuracy | Precision | Recall | F1 Score | ROC AUC Score |
|--------------------|----------|-----------|--------|----------|---------------|
| Logistic Regression | 0.79     | 0.51      | 0.65   | 0.57     | 0.82          |
| Random Forest       | 0.92     | 0.87      | 0.75   | 0.80     | 0.93          |
| XGBoost             | 0.92     | 0.89      | 0.72   | 0.80     | 0.93          |

### Model Selection
- XGBoost and Random Forest had similar performance (Accuracy, F1 Score, and ROC AUC Score).
- XGBoost had a slightly higher Precision, while Random Forest had a slightly higher Recall.
- Given the similar performance, both models were saved for potential future use.

### Final Model
Random Forest was selected as the best model due to its slightly higher recall, which is important for identifying as many high-risk borrowers as possible. However, the XGBoost model was also saved for future analysis and potential use.

## Future Improvements
- Hyperparameter tuning for both Random Forest and XGBoost to further improve performance (e.g., using GridSearchCV or RandomizedSearchCV).
- Deploy the model using a web application (e.g., Flask or Streamlit) to allow users to input borrower information and receive a default risk prediction.

## Project Structure
```
credit-risk-project/
|
├── data/
|   ├── clean_credit_risk_dataset.csv
|   ├── credit_risk_dataset.csv
├── notebooks/
|   ├── 1. credit_risk_eda.ipynb
|   ├── 2. credit_risk_feat_eng.ipynb
|   └── 3. credit_risk_ml.ipynb
├── model/
|   ├── rf_model.joblib
|   ├── scaler.joblib
|   ├── xgb_model.joblib
|
├── requirements.txt
└── README.md
```

## Conclusion
This project displays an end-to-end data science workflow for default risk prediction, from data exploration and feature engineering to machine learning modeling and evaluation. By comparing multiple models and selecting the best model based on performance metrics, the project highlights how machine learning can be utilized in real-world financial applications to support better decision-making.

## Author
Aaron Thomas