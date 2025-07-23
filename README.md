# credit-card-fraud-detection

This project analyzes and visualizes credit card transaction data to understand patterns related to fraud detection


## Objectives

- Perform structured **EDA** on credit card transaction data.
- Visualize patterns of fraudulent vs. legitimate transactions across:
  - Transaction times
  - Transaction amounts
  - Hourly distributions
- Understand challenges caused by **extreme class imbalance**.
- Identify patterns to inform future modeling.



## Dataset

- **Source:** [Kaggle Credit Card Fraud Detection](https://www.kaggle.com/mlg-ulb/creditcardfraud)
- **Shape:** 284,807 transactions, 31 features
- **Target:**
  - `Class = 0` → Legitimate (284,315 transactions)
  - `Class = 1` → Fraudulent (492 transactions, ~0.172%)
- PCA-transformed anonymized features `V1–V28`, `Time`, `Amount`.

---

## Process Followed

1️. **Data Loading & Cleaning**
- Loaded data with pandas.
- Checked data types and null values (none found).

2️. **Data Exploration**
- Verified **high class imbalance** in fraud vs. non-fraud transactions.
- Analyzed distributions of fraudulent transactions over time.

3️. **Feature Engineering**
- Created a new `Hour` feature by converting `Time` in seconds to hourly buckets.

4️. **Visualization**
- Bar plots to visualize fraud vs. non-fraud count.
- Time density plots for fraudulent and non-fraudulent transactions.
- Hourly aggregation:
  - Total transaction amounts
  - Number of transactions
  - Minimum, maximum, and median transaction amounts



## Key Insights

- Fraudulent transactions are **evenly distributed throughout the day**, unlike legitimate transactions, which show activity peaks during typical business hours.

- Fraud can occur **at low-activity times (night hours)**, indicating fraudsters do not follow standard transaction patterns.

- Fraudulent transactions are **not always high-value**; there is variability, requiring attention to smaller transactions during fraud detection.

- **Severe class imbalance** suggests that model evaluation in the future should prioritize precision-recall and ROC-AUC rather than plain accuracy.



## Visuals

- Matplotlib and Seaborn for static plots.
- Plotly for interactive time distribution visualizations.


