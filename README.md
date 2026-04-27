# 🐟 Fish Weight Prediction - Machine Learning Regression Project

![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)
![Machine Learning](https://img.shields.io/badge/Machine%20Learning-Regression-green.svg)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Used-orange.svg)
![Status](https://img.shields.io/badge/Status-Completed-success.svg)

## 📌 Project Overview

This project focuses on predicting the weight of fish based on their physical measurements using supervised machine learning regression techniques.

The dataset contains multiple fish species with features such as length measurements, height, width, and species type. The goal is to build a model that accurately estimates fish weight using these attributes.

This project includes:
- Data cleaning and preprocessing
- Exploratory Data Analysis (EDA)
- Feature engineering and inconsistency handling
- Model training (Linear Regression and Random Forest)
- Hyperparameter tuning
- Model evaluation and comparison
- Feature interpretation (coefficients + feature importance)

---

## 📂 Dataset Description

The dataset contains the following features:

- Species: Type of fish (categorical variable)
- Weight: Target variable (grams)
- Length1: Vertical length
- Length2: Diagonal length
- Length3: Cross length
- Height: Height of fish body
- Width: Width of fish body

### ⚠️ Data Issues Identified
- Missing values in multiple features
- Inconsistent category naming (e.g., Beam vs Bream)
- Invalid target value (Weight = 0)
- High correlation between length features (multicollinearity)

---

## 🧹 Data Preprocessing Steps

### 1. Handling missing values
Missing values were detected across several features and handled using appropriate imputation strategies depending on feature type.

### 2. Fixing inconsistencies
Incorrect categorical labels were corrected to ensure consistency in the Species column.

### 3. Removing invalid records
Rows with invalid target values (Weight ≤ 0) were removed because the target variable cannot be imputed.

### 4. Feature selection preparation
Highly correlated features were analyzed for multicollinearity impact.

---

## 📊 Exploratory Data Analysis (EDA)

Key insights discovered:

- Fish weight distribution is right-skewed
- Large variation exists in fish sizes
- Length features are highly correlated
- Width and height show strong predictive potential
- Species has weaker direct impact compared to physical measurements

---

## 🤖 Machine Learning Models Used

### 1. Linear Regression 📈
- Used as baseline model
- Assumes linear relationship between features and target
- Sensitive to multicollinearity

### 2. Random Forest Regressor 🌳
- Ensemble tree-based model
- Captures non-linear relationships
- Handles multicollinearity and outliers well

---

## ⚙️ Hyperparameter Tuning

Random Forest was optimized using GridSearchCV.

Best parameters:
- n_estimators: 100
- max_depth: None
- min_samples_split: 5
- min_samples_leaf: 1

---

## 📏 Model Evaluation

### Linear Regression Results
- Strong baseline performance
- R² ≈ 0.88 on test data
- Limited by linear assumptions and correlated features

### Random Forest Results
- Strong improvement over Linear Regression
- R² ≈ 0.95 on test data
- Lower prediction error (MAE and RMSE)
- Slight overfitting reduced after tuning

---

## 📊 Final Model Comparison

| Model               | MAE   | RMSE  | R²    |
|--------------------|-------|-------|-------|
| Linear Regression   | Higher | Higher | Lower |
| Random Forest       | Lower  | Lower  | Higher |

### 🏆 Final Selected Model
Random Forest Regressor (Tuned)

---

## 🔍 Model Interpretation

### Linear Regression (Coefficients)
- Shows direction of relationship (positive/negative)
- Strong influence from length features
- Multicollinearity affects interpretation

### Random Forest (Feature Importance)
- Width is the most influential feature
- Length features contribute moderately
- Species has minimal impact

---

## 🧠 Key Insights

- Fish weight is primarily determined by physical size
- Width is the strongest predictor in tree-based models
- Length features are highly correlated
- Species has minimal predictive power compared to physical measurements
- Non-linear models outperform linear models for this dataset

---

## 🚀 Final Model Pipeline

1. Data cleaning and preprocessing  
2. Feature selection and encoding  
3. Train-test split  
4. Model training (Linear Regression + Random Forest)  
5. Hyperparameter tuning (GridSearchCV)  
6. Evaluation and comparison  
7. Final model retraining on full dataset  

---

## 💾 Model Deployment Preparation

After selecting the final model:
- The model was retrained on the full dataset
- Prepared for real-world prediction usage
- Saved for future inference tasks

---

## 🛠️ Technologies Used

- Python 🐍
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn

---

## 📌 Conclusion

This project demonstrates a complete machine learning pipeline from raw data to final model selection. Random Forest was selected as the final model due to its superior predictive performance and ability to handle non-linear relationships in the dataset.
