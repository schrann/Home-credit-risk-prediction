# Predictive Credit Risk Management

## Problem Statement

Loan default risk poses significant financial threats to lenders, and effective prediction mechanisms are essential to mitigate these risks. This project addresses the challenge of predicting loan defaults using historical customer application data. By analyzing demographic, financial, and credit history attributes, we build robust machine learning models to forecast the likelihood of default.

---

## Data Preprocessing

1. **Handling Missing Values**:
   - Dropped columns with >40% missing values.
   - Imputed remaining missing values with:
     - Median for numerical features.
     - Mode for categorical features.

2. **Feature Engineering**:
   - Created derived features such as:
     - `CREDIT_INCOME_PERCENT`: Credit amount to income ratio.
     - `ANNUITY_INCOME_PERCENT`: Annuity to income ratio.
     - `CREDIT_GOODS_DIFF`: Difference between credit amount and goods price.

3. **Encoding**:
   - Categorical variables like `CODE_GENDER` and `FLAG_OWN_CAR` were binary-encoded.

---

## Key Insights

- Young males with low income and lower education levels are at higher risk of default.
- Applicants on maternity leave are less likely to repay, suggesting loan reduction for such cases.
- Loans for repairs and urgent needs have higher default rates.
- Business owners, students, and higher-educated individuals are reliable borrowers.
- Loans for buying homes or garages show lower default tendencies.

---

## Model Building and Results

| Model                | ROC-AUC | Key Observations                  |
|----------------------|---------|-----------------------------------|
| Logistic Regression  | 0.60    | Baseline model                   |
| Decision Tree        | 0.71    | Slight overfitting after tuning  |
| Random Forest        | 0.747   | Improved with hyperparameter tuning |
| XGBoost              | 0.756   | Better handling of class imbalance |
| LightGBM             | **0.76**| Best performance with balanced recall scores (0.69 for both classes) |

---

## Challenges

1. **Imbalanced Dataset**:
   - Required precision in handling class imbalances to improve recall.
2. **Computational Limitations**:
   - Large dataset size constrained hyperparameter optimization via GridSearchCV.

---

## Future Enhancements

1. **AWS/Cloud Integration**:
   - Implement cloud-based data management and model deployment for scalability.

2. **Interactive Web Application**:
   - Build a user-friendly web interface for real-time credit risk prediction and visualization.

Feel free to contact me for further clarifications!
