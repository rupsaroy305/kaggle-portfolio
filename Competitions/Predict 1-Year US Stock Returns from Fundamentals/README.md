#  Stock Return Prediction with CatBoost

A baseline machine learning solution for predicting **1-year forward returns of US-listed stocks** using company fundamental data derived from SEC filings.

This project was developed as part of a Kaggle competition and demonstrates an end-to-end regression workflow using **CatBoost**, including exploratory data analysis, preprocessing, grouped cross-validation, feature importance analysis, and submission generation.

---

##  Notebook

**Kaggle Notebook:** [*Click Here*](https://www.kaggle.com/code/rupsarroy/forecasting-stock-returns-with-catboost)

---

##  Competition

**Competition:** [*Click Here*](https://www.kaggle.com/competitions/predict-1-year-us-stock-returns-from-fundamentals/overview)

---

##  Dataset

The dataset contains quarterly fundamental financial information for approximately **2,000 US-listed companies** between **2019 and 2022**. Each observation represents a stock-quarter snapshot with financial ratios, profitability metrics, balance sheet variables, growth indicators, and valuation measures.

The objective is to predict the **1-year forward stock return (`return_pct`)** for unseen observations in the test set.

---

##  Project Workflow

* Data loading and exploration
* Missing value analysis
* Exploratory Data Analysis (EDA)
* Correlation analysis
* Feature importance analysis
* Data preprocessing
* Grouped cross-validation using **GroupKFold**
* CatBoost regression modeling
* Hyperparameter experimentation
* Prediction generation
* Kaggle submission creation

---

##  Model

* **Algorithm:** CatBoost Regressor
* **Task:** Regression
* **Evaluation Metric:** RMSE (Root Mean Squared Error)
* **Validation Strategy:** GroupKFold (grouped by stock ticker)

Multiple CatBoost configurations were evaluated by varying model depth, learning rate, regularization, and boosting iterations. The final model was selected based on cross-validation performance.

---

##  Files

* `Stock Return Prediction | CatBoost V1.ipynb` — Complete notebook
* `submission.csv` — Competition submission file

---

##  Libraries

* Python
* Pandas
* NumPy
* Matplotlib
* Scikit-learn
* CatBoost

---

##  Key Topics

* Regression
* Financial Data Analysis
* Stock Return Prediction
* CatBoost
* Feature Importance
* Cross Validation
* Machine Learning
* Tabular Data
* Exploratory Data Analysis (EDA)

---

##  Future Improvements

* XGBoost implementation
* LightGBM implementation
* Advanced feature engineering
* Hyperparameter optimization
* Model ensembling
* Stacking and blending

---

##  License

This project is intended for educational purposes and Kaggle competition participation.
