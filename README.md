# Practical_Lab2_CSCN8010
Multivariate Linear Regression, Non-Parametric Models and Cross-Validation
##  Objective
This project aims to build and evaluate regression models that can best predict **the risk of diabetes progression** using the Scikit-learn Diabetes dataset.  
The final model can be used as a **screening tool for physicians** to identify patients at risk.

##  Models to Explore
1. **Univariate Polynomial Regression**
2. **Multivariate Polynomial Regression**
3. **Decision Trees**
4. **k-Nearest Neighbors (kNN)**

##  Evaluation Metrics
- R² (Coefficient of Determination)
- Mean Absolute Percentage Error (MAPE)
- Mean Absolute Error (MAE)

##  Workflow (Part 1)
1. Load the Diabetes dataset from Scikit-learn  
2. Perform **Exploratory Data Analysis (EDA)**  
3. Clean the data  
4. Split into Train (75%), Validation (10%), and Test (15%) sets

##  Dataset Overview

The **Diabetes dataset** is a classic regression dataset available in Scikit-learn.  
It contains **442 samples** and **10 baseline variables**, all numeric and standardized.

**Features:**
- Age, Sex, BMI, Blood Pressure, and six blood serum measurements.  

**Target:**
- `disease_progression`: Quantitative measure of diabetes progression one year after baseline (continuous numeric value).


##  Data Cleaning Notes

- The dataset is **pre-cleaned and standardized** by Scikit-learn.
- **No missing values** or duplicates were found.
- Outliers are minimal due to z-score standardization (|z| < 3 for almost all points).
- Therefore, **no transformations or imputations** are necessary at this stage.

#  Part 2 — Univariate Polynomial Regression on BMI

We now build **univariate polynomial regression models** using the BMI feature (`bmi`)  
to predict **disease progression one year after baseline**.

We’ll fit **six models** of polynomial degrees **0 through 5**, evaluate them using:
- R² (Coefficient of Determination)  
- MAE (Mean Absolute Error)  
- MAPE (Mean Absolute Percentage Error)

We’ll then identify the best model based on **validation performance**.

#  Part 3 — Multivariate and Non-Parametric Models

We now extend our analysis beyond the univariate BMI model to include multiple predictors
and non-parametric methods.  
Each family of models will have **two variants** with different hyperparameters:

| Model Type | Variants |
|-------------|-----------|
| Polynomial Regression | Degree 2, Degree 3 |
| Decision Tree | max_depth = 3, max_depth = 5 |
| k-Nearest Neighbors | k = 3, k = 7 |
| Linear Regression Variants | LinearRegression, Ridge Regression (α=1.0) |

Each model will be trained and validated using the same train/validation split,
and evaluated using **R²**, **MAE**, and **MAPE**.

#  Part 4 — Best Model: Test Evaluation & Visualization

After comparing all models on the training and validation data,  
we now select the **best-performing model** (based on highest Validation R² and lowest MAE/MAPE)  
and evaluate it on the **Test set** to confirm its generalization capability.

We'll also visualize how well the predictions align with the true disease progression values.
