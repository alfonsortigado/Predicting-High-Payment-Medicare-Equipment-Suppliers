# Predicting-High-Payment-Medicare-Equipment-Suppliers
# Predicting High-Payment Medicare Equipment Suppliers

This project applies machine learning to identify high-cost suppliers in the Medicare Durable Medical Equipment, Prosthetics, Orthotics, and Supplies (DMEPOS) program. Using a dataset provided by the Centers for Medicare & Medicaid Services (CMS), we train a classifier to predict whether a supplier belongs to the top 25% in terms of standardized Medicare payment amounts.

## Dataset

- **Source**: CMS DMEPOS Supplier Payment Public Use File (PUF)
- **File**: `mup_dme_ry25_p05_v10_dy23_supr.csv`
- **Observations**: 63,988
- **Features**: 93, including:
  - Supplier demographics
  - Service volumes and claims
  - Submitted charges and payments
  - Patient population characteristics (age, race, comorbidities)

## Objective

To build a predictive model that can classify suppliers as:
- `1` = High Payment Supplier (above 75th percentile of standardized payments)
- `0` = Not High Payment

This allows for:
- Risk stratification and audit targeting
- Monitoring supplier billing behavior
- Supporting data-driven payment integrity efforts

## ⚙️ Workflow Summary

1. **Data Cleaning and Preparation**
   - Removed irrelevant ID/location columns
   - Imputed missing values with the median
   - Encoded categorical variables using one-hot encoding
   - Normalized data for logistic regression

2. **Exploratory Data Analysis**
   - Summary statistics and missing value inspection
   - Correlation analysis
   - Class imbalance review

3. **Model Training and Comparison**
   - Algorithms tested:
     - Logistic Regression
     - Random Forest
     - Gradient Boosting
     - Decision Tree
     - Naive Bayes
     - Support Vector Machine
   - Stratified train/test split
   - Evaluation metrics: Accuracy, Precision, Recall, F1, ROC-AUC

4. **Model Selection**
   - **Gradient Boosting** selected as the final model:
     - Accuracy: 95.5%
     - Precision: 97.7%
     - Recall: 91.4%
     - ROC-AUC: **0.9878**
   - Top predictive features include:
     - Number of beneficiaries (`Tot_Suplr_Benes`)
     - Standardized POS Medicare payments
     - Count of HCPCS codes billed
     - Number of male patients
     - DME payment totals

## Key Insights

- Volume and diversity of services, as well as patient mix, are strong predictors of high Medicare payments.
- Gradient Boosting effectively captures non-linear interactions and outperforms simpler models in recall and AUC.
- Feature importance aligns with expected operational drivers, enhancing interpretability.

## Repository Structure
├── Predicting High-Payment Medicare Equipment Suppliers.ipynb
├── mup_dme_ry25_p05_v10_dy23_supr.csv
└── README.md



## References

- [CMS Public Use Files Portal](https://data.cms.gov/provider-data/)
- [scikit-learn documentation](https://scikit-learn.org/)



