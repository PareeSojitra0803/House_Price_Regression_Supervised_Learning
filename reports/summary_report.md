<h1 align="center">House Price Prediction – Summary Report</h1>

<p align="center">
Supervised Machine Learning • Regression Analysis • Executive Summary
</p>

---

## 1. Business Problem & Dataset

### Theory

Accurate property valuation is essential for buyers, sellers, and real estate businesses to make informed decisions. Manual valuation methods are often subjective and may fail to capture complex relationships between property characteristics and market prices. The objective of this project was to develop an end-to-end supervised machine learning regression pipeline capable of accurately predicting residential house prices.

The project uses the **Ames Housing Dataset**, which contains **1,460 residential properties**, **80 explanatory features**, and one target variable (**SalePrice**). The dataset includes structural, quality, neighborhood, and location-related information that strongly influences property valuation.

**Observation**

The dataset provides sufficient feature diversity to build and compare multiple regression models while evaluating the impact of different preprocessing and feature engineering techniques.

---

## 2. Data Preprocessing & Feature Engineering

### Theory

Several preprocessing techniques were applied to improve model performance and data quality:

- Missing values were handled using domain-specific imputation strategies.
- Numerical missing values were filled using median or zero where appropriate.
- Categorical missing values representing the absence of a feature were replaced with **"None"**.
- Highly skewed numerical features and the target variable were transformed using **log1p()**.
- Two influential outliers were removed based on **GrLivArea** and **SalePrice**.
- New features such as **TotalSF**, **HouseAge**, **RemodAge**, **HasGarage**, and **HasPool** were created.
- Ordinal Encoding, One-Hot Encoding, and StandardScaler were applied using a unified **ColumnTransformer** and **Pipeline**.

**Observation**

Feature engineering and proper preprocessing significantly improved data consistency, reduced skewness, and produced a cleaner dataset for model training.

---

## 3. Model Evaluation

Five regression models were trained and compared:

- Linear Regression
- Ridge Regression
- Lasso Regression
- Random Forest Regressor
- XGBoost Regressor

### Best Model Performance

| Metric | XGBoost |
|---------|---------:|
| RMSE | **19,447.14** |
| MAE | **13,994.36** |
| R² Score | **0.9315** |

Hyperparameter tuning was performed using **RandomizedSearchCV**, resulting in improved model generalization and predictive accuracy.

**Observation**

Among all evaluated models, **XGBoost Regressor** produced the lowest prediction error and the highest R² Score, making it the most reliable model for deployment.

---

## 4. Business Insights

The three most influential features identified by the final model were:

1. **OverallQual** – Houses with better construction quality consistently achieved higher selling prices.
2. **GrLivArea** – Larger above-ground living space strongly increased property value.
3. **Neighborhood** – Property location remained one of the most significant pricing factors because of accessibility, amenities, and local demand.

**Observation**

These findings suggest that property quality, usable living space, and location should be prioritized by real estate professionals when estimating residential property values.

---

## 5. Conclusion & Future Scope

The project successfully developed a complete supervised machine learning pipeline for residential house price prediction. After comparing multiple regression algorithms, **XGBoost** demonstrated the best predictive performance and was selected as the final deployment model.

Future improvements may include:

- Expanding the dataset with additional property transactions.
- Incorporating geospatial and economic indicators.
- Exploring advanced ensemble methods such as LightGBM and CatBoost.
- Applying Bayesian Optimization for hyperparameter tuning.
- Deploying the trained pipeline as a real-time Streamlit web application for interactive house price prediction.

**Observation**

The developed pipeline demonstrates strong predictive performance and provides a practical foundation for deployment in real-world real estate valuation systems.