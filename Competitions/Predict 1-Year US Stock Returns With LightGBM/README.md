# Decoding Market Signals: Predicting Stock Returns with LightGBM

> An end-to-end machine learning pipeline for predicting stock returns using financial fundamentals, data preprocessing, and LightGBM regression.

---

##  Overview

Predicting stock returns is a challenging regression problem due to noisy financial data, missing values, and extreme market movements. This project builds a robust machine learning pipeline that leverages company financial metrics to forecast future stock returns.

The workflow covers the complete machine learning lifecycle from exploratory data analysis and preprocessing to model training, evaluation, and Kaggle submission generation.

---


##  Notebook

**Kaggle Notebook:** [*Click Here*](https://www.kaggle.com/code/rupsarroy/decoding-market-signals-with-lightgbm)

---

##  Competition

**Predict 1-Year US Stock Returns from Fundamentals:** [*Click Here*](https://www.kaggle.com/competitions/predict-1-year-us-stock-returns-from-fundamentals/overview)

---

##  Dataset

The target variable is:

```text
return_pct
```

which represents the future percentage return of each stock.

---

##  Features

-  Comprehensive Exploratory Data Analysis (EDA)
-  Missing value analysis and median imputation
-  Dataset quality checks (duplicates, feature inspection)
-  Train vs Test feature comparison
-  Target distribution and outlier analysis
-  Target clipping to reduce extreme skewness
-  LightGBM Regression model
-  Cross-validation using RMSE
-  Automated Kaggle submission generation

---

##  Workflow

```
Load Dataset
      │
      ▼
Exploratory Data Analysis
      │
      ▼
Missing Value Analysis
      │
      ▼
Feature Selection
      │
      ▼
Median Imputation
      │
      ▼
Baseline LightGBM
      │
      ▼
Cross Validation
      │
      ▼
Target Distribution Analysis
      │
      ▼
Target Clipping
      │
      ▼
Improved LightGBM Model
      │
      ▼
Prediction
      │
      ▼
Submission.csv
```

---

**Exploratory Data Analysis**

The notebook investigates:

- Dataset dimensions
- Feature types
- Missing values
- Duplicate records
- Train vs Test differences
- Distribution of financial variables
- Ticker consistency

A key observation was that the **training dataset contains real stock tickers**, while the **test dataset contains anonymized ticker IDs**. Consequently, the ticker feature was excluded from modeling.

---

**Data Preprocessing**

The preprocessing pipeline includes:

- Removing identifier columns
  - `id`
  - `ticker`
  - `period_start`
  - `period_end`

- Separating features and target

- Filling missing numerical values using

```python
SimpleImputer(strategy="median")
```

Median imputation was chosen because financial variables contain numerous outliers.

---

**Model**

The primary model used is:

- **LightGBM Regressor**

Configured with:

- 500 estimators
- Learning rate = 0.05
- 31 leaves

Performance was evaluated using **5-Fold Cross Validation** with Root Mean Squared Error (RMSE).

---

**Target Engineering**

One of the largest performance improvements came from analyzing the target distribution.

The target exhibited:

- Heavy positive skewness
- Large number of extreme outliers
- Maximum return exceeding **10,000%**

To reduce their impact, the target was clipped between the **0.5th** and **99.5th** percentiles before retraining the model.

This substantially improved validation performance.

---
##  Competition Results

| Metric | Score |
|--------|------:|
| **Public Score** | 15184.81575 |
| **Leaderboard Rank** | 115 / 334 |
| **Model** | LightGBM Regressor |
| **Evaluation Metric** | RMSE |


---

##  Technologies Used

| Category | Tools |
|----------|------|
| Language | Python |
| Data Analysis | Pandas, NumPy |
| Visualization | Matplotlib, Seaborn |
| Machine Learning | LightGBM, Scikit-learn |
| Validation | K-Fold Cross Validation |
| Environment | Jupyter Notebook |

---

##  Project Structure

```
├── decoding-market-signals-with-lightgbm.ipynb
│
├── submission.csv
│
├── README.md
```

---


##  Key Takeaways

- Financial datasets contain significant missing data that must be handled carefully.
- Median imputation provides a simple yet effective preprocessing strategy.
- Target distribution plays a critical role in regression performance.
- Reducing extreme outliers through target clipping can dramatically improve model accuracy.
- A well-designed preprocessing pipeline often contributes as much as the model itself.

---
