#  Stellar Object Classification with CatBoost

A machine learning project for classifying astronomical objects into **GALAXY**, **QSO**, and **STAR** using photometric measurements, redshift, and spectral information. The notebook uses **CatBoost** with astronomy-inspired feature engineering and stratified cross-validation.

## Notebook

**Kaggle Notebook:** [Click Here](https://www.kaggle.com/code/rupsarroy/catboost-astronomical-features-96-64-oof)


## Competition

**Kaggle Competition Page:** [Click Here](https://www.kaggle.com/competitions/playground-series-s6e6)

## Features

* Astronomy-inspired feature engineering
* Color index creation (`u-g`, `g-r`, `r-i`, `i-z`)
* Extended color features
* Magnitude-based statistical features
* Native categorical feature handling with CatBoost
* Stratified 5-Fold Cross Validation
* Out-of-Fold (OOF) evaluation
* Competition-ready submission generation

## Model

* CatBoost Classifier

## Feature Engineering

The following engineered features were added:

* Color indices
* Extended color indices
* Mean magnitude
* Standard deviation of magnitudes
* Minimum magnitude
* Maximum magnitude
* Magnitude range

## Validation

* **Validation Strategy:** Stratified 5-Fold Cross Validation
* **OOF Accuracy:** **96.64%**

## Technologies Used

* Python
* Pandas
* NumPy
* Scikit-learn
* CatBoost

## Project Structure

```
.
├── catboost-astronomical-features-96-64-oof.ipynb
├── README.md
└── submission.csv
```

## Results

The enhanced CatBoost model achieved an **OOF Accuracy of 96.64%**, providing a strong baseline for the Kaggle Playground Series S6E6 competition.

**Private Leaderboard Score:** **0.95380**


## Future Improvements

* Hyperparameter optimization
* LightGBM implementation
* XGBoost implementation
* Ensemble learning
* Additional astrophysical feature engineering
* Pseudo-labeling

## License

This project is intended for educational and portfolio purposes.
