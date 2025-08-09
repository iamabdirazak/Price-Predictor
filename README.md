# California Housing Prices — Price Prediction

## 📌 Project Overview

This project predicts median house values for California districts using the **California Housing Prices Dataset** from Kaggle.  
It’s a **regression problem** where the goal is to understand how location, demographics, and housing characteristics influence prices — and to build a model that can predict them.

We cover the **full data science pipeline**:

1. **Data Understanding**
2. **Data Cleaning**
3. **Exploratory Data Analysis (EDA)**
4. **Feature Engineering & Transformation**
5. **Modeling**
6. **Hyperparameter Tuning**
7. **Evaluation & Insights**

---

## 1️⃣ Data Understanding

- Dataset: `housing.csv`
- Rows: ~20,000
- Columns: Housing, population, income, location, proximity to ocean.

Target: **`median_house_value`** (continuous variable)

---

## 2️⃣ Data Cleaning

- Handled missing values in `total_bedrooms` (median imputation).
- Removed duplicate rows.
- Checked for unrealistic zero values in numeric columns.
- Ensured correct data types (categorical vs numeric).
- Verified valid ranges (e.g., latitude/longitude for California).

---

## 3️⃣ Exploratory Data Analysis

- **Distributions**: Found skewed variables (`total_rooms`, `population`, etc.).
- **Correlations**: `median_income` had the strongest positive correlation with house value.
- **Geographic patterns**: Prices higher near the coast & in certain latitude/longitude ranges.
- **Outliers**: `median_house_value` capped at 500,001 — dataset limitation.

---

## 4️⃣ Feature Engineering

Created ratio features to capture housing relationships:

- `rooms_per_household`
- `bedrooms_per_room`
- `population_per_household`

Applied **log transformations** to skewed numeric features.

---

## 5️⃣ One-Hot Encoding

Converted `ocean_proximity` into dummy variables for modeling.

---

## 6️⃣ Modeling

We compared:

- **Linear Regression** — interpretable baseline.
- **Random Forest** — robust non-linear model.
- **Gradient Boosting** — strong sequential ensemble.

---

## 7️⃣ Hyperparameter Tuning

Used **GridSearchCV** to optimize RandomForest and GradientBoosting:

- Tuned number of trees, depth, learning rate, and minimum samples per split/leaf.
- Improved accuracy & reduced RMSE.

---

## 8️⃣ Results

| Model                     | RMSE | R²  |
| ------------------------- | ---- | --- |
| Linear Regression         | ...  | ... |
| Random Forest             | ...  | ... |
| Gradient Boosting         | ...  | ... |
| Random Forest (Tuned)     | ...  | ... |
| Gradient Boosting (Tuned) | ...  | ... |

---

## 9️⃣ Key Insights

- **Income level** is the single strongest predictor of housing prices.
- Proximity to the ocean boosts property value.
- Engineered ratios improved model performance.
- Gradient Boosting (tuned) outperformed others with the lowest RMSE.

---

## 🔍 Why Models Perform Differently

- **Linear Regression** works best with simple, linear relationships.
- **Random Forest** captures non-linear patterns but treats all trees equally.
- **Gradient Boosting** learns sequentially, correcting errors, and often outperforms Random Forest in structured datasets like this.

---

## 🚀 Future Improvements

- Try **XGBoost** or **LightGBM** for faster and potentially more accurate results.
- Incorporate external datasets (e.g., economic indicators, crime rates).
- Deploy model via a web app for real-time predictions.

---

**Author**: Abdirazak Mubarak
**Dataset**: [California Housing Prices](https://www.kaggle.com/datasets/camnugent/california-housing-prices)
