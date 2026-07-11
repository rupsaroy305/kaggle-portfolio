#  Non-Parametric 3D Spatial KNN and IDW Interpolation for Wellbore TVT Prediction

A lightweight, training-free approach for **True Vertical Thickness (TVT)** prediction in the **ROGII Wellbore Geology Prediction** competition.

Instead of relying on machine learning models, this project leverages the spatial continuity of geological formations by combining **3D K-Nearest Neighbors (KNN)**, **Inverse Distance Weighting (IDW)**, and trajectory smoothing to estimate TVT directly from neighboring well observations.

---

##  Notebook

**Kaggle ROGII Notebook:**: [Click Here](https://www.kaggle.com/code/rupsarroy/non-para-3d-spatial-knn-and-idw-interpolation)

This project explores how far purely spatial reasoning can be pushed before introducing supervised machine learning, providing a strong foundation for more advanced geological prediction pipelines.

---

##  Competition

**ROGII Wellbore Geology Prediction**: [Click Here](https://www.kaggle.com/competitions/rogii-wellbore-geology-prediction)

---

##  Project Overview

The central hypothesis behind this approach is that wells drilled within the same geological field exhibit similar structural characteristics. Consequently, unknown TVT values can be estimated from nearby training wells using only their spatial relationships.

Unlike conventional machine learning pipelines, this method:

-  Requires **no model training**
-  Uses **no feature engineering**
-  Has **no hyperparameter optimization**
-  Relies entirely on spatial interpolation

This makes it a strong deterministic baseline for comparing against more sophisticated machine learning approaches.

---

##  Methodology

The prediction pipeline consists of the following stages:

### 1. Load Geological Anchor Points

Known TVT observations from every training well are collected to form a global set of geological anchor points.

Each anchor contains:

- X coordinate
- Y coordinate
- Z coordinate
- Measured Depth (MD)
- Known TVT

---

### 2. Construct a 3D KD-Tree

A KD-Tree is built over the spatial coordinates of all training anchors.

To better capture geological variation, the **Z-coordinate is weighted more heavily** than the horizontal coordinates during neighbor search.

---

### 3. 3D K-Nearest Neighbor Search

For every unknown point in a test well:

- Query the KD-Tree
- Retrieve the **K nearest geological neighbors**
- Compute spatial distances

---

### 4. Inverse Distance Weighted (IDW) Interpolation

Neighboring TVT values are combined using **Inverse Distance Weighting (IDW²)**.

Nearby observations contribute more strongly, while distant observations have progressively smaller influence.

---

### 5. Trajectory Smoothing

Predictions are smoothed along the measured depth (MD) using a rolling average to reduce local interpolation noise.

---

### 6. Drift Correction

The predicted trajectory is compared with the **last known TVT measurement** within each well.

If the interpolated sequence deviates excessively from this geological anchor, the predictions are shifted back toward the observed trajectory to maintain continuity.

---

### 7. Final Post-processing

A **Savitzky–Golay filter** is applied independently to each well to generate smoother and more geologically realistic TVT curves before submission.

---

##  Repository Structure

```text
├── non-para-3d-spatial-knn-and-idw-interpolation.ipynb
├── submission.csv
├── README.md
```

---

##  Technologies Used

- Python
- NumPy
- Pandas
- SciPy
- cKDTree
- Savitzky–Golay Filter

---

##  Key Features

- Geometry-based prediction
- 3D spatial nearest-neighbor search
- Inverse Distance Weighting interpolation
- Depth-aware trajectory smoothing
- Zero model training
- Fast inference using KD-Tree indexing

---

##  Results

 **Public Leaderboard Score:**  **165.426** 

This notebook establishes a **geometry-driven baseline** for the ROGII Wellbore Geology Prediction challenge. While it does not rely on machine learning, it demonstrates the predictive capability of purely spatial interpolation using **3D K-Nearest Neighbors (KNN)**, **Inverse Distance Weighting (IDW)**, and trajectory smoothing.

---

##  Future Improvements

This notebook serves as a deterministic baseline. Future iterations may incorporate:

- Dynamic Time Warping (DTW)
- Particle Filtering
- Beam Search
- Wavelet-based geological features
- CatBoost / LightGBM / XGBoost ensembles
- Hybrid spatial + machine learning models

---

