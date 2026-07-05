# TVT Prediction with HistGradientBoosting

Machine learning pipeline for predicting **True Vertical Thickness (TVT)** from wellbore trajectory and geological measurements. The project includes exploratory data analysis, feature engineering, model training, validation, and competition-ready prediction generation using HistGradientBoostingRegressor.

## Notebook

**Kaggle Notebook:** [Click Here](https://www.kaggle.com/code/rupsarroy/tvt-prediction-with-histgradientboosting-eda-fe)

## Competition

**Rogii Wellbore Geology Prediction:** [Click Here](https://www.kaggle.com/competitions/rogii-wellbore-geology-prediction/overview)

## Key Topics

* True Vertical Thickness (TVT) prediction
* Regression
* Exploratory Data Analysis (EDA)
* Feature Engineering
* HistGradientBoostingRegressor
* Model Evaluation
* Competition Submission

## Workflow

* Data loading and preprocessing
* Exploratory Data Analysis (EDA)
* Missing value analysis
* Correlation analysis
* Feature engineering
* Geometry-based feature creation
* Rolling statistical features
* Difference features
* Type-well aggregated features
* Model training with HistGradientBoostingRegressor
* Validation using RMSE
* Final model retraining
* Submission file generation

## Features Engineered

* Relative measured depth
* Distance from well start
* Spatial displacement features (`dx`, `dy`, `dz`)
* Horizontal distance (`xy_distance`)
* Rolling mean, standard deviation, minimum and maximum of Gamma Ray (GR)
* GR difference and depth difference features
* Type-well statistical features (mean, standard deviation, minimum, maximum, row count)

## Model

* **Algorithm:** HistGradientBoostingRegressor
* **Objective:** Predict True Vertical Thickness (TVT)
* **Validation Metric:** Root Mean Squared Error (RMSE)

## Results

* **Validation RMSE:** **9.00095**
* **Public Score:** **683.246**


## Libraries Used

* Python
* NumPy
* Pandas
* Matplotlib
* Scikit-learn

## Repository Structure

```text
ROGII Wellbore Geology Prediction/
│
├── tvt-prediction-with-histgradientboosting-eda-fe.ipynb
├── README.md
└── submission.zip (generated)
```

## Future Improvements

* GroupKFold cross-validation
* CatBoost and LightGBM comparison
* Additional sequential and lag features
* Hyperparameter optimization
* Ensemble learning
* Advanced spatial feature engineering
