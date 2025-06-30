### 🥈 Second Place Solution for the DSN Free AI Classes in Every City 2025 Hackathon

This project was developed for a challenge hosted by **Zindi** using **Google Colab**. The objective was to build a regression-based solution to identify which products are most likely to be returned at **Impact Stores**, a Nigerian retail chain with over 1,500 products. The insights are intended to guide strategic expansion decisions.

---

### 🎯 Core Objective

Predict **item return volumes** using regression models.

After experimenting with several algorithms—**Ridge Regression**, **Lasso Regression**, **Support Vector Regressor (SVR)**, **Decision Trees**, and **Linear Regression**—I found **Lasso Regression** with an `alpha` value of **60.5** delivered the best performance, based on **Root Mean Squared Error (RMSE)**.

---

### 🔄 ETL Pipeline

#### 📥 Extract

* Loaded raw `train.csv` and `test.csv` files containing customer, product, and order data.

#### 🔧 Transform

* Applied mathematical transformations to reduce skew:

  * `log`, `reciprocal`, `sqrt`, `cube_root`
* Encoded categorical features using **One-Hot Encoding**.
* Generated **Polynomial Features** (degree = 2) to capture non-linear interactions.
* Normalized the final feature set using **StandardScaler**.

#### 📤 Load

* Transformed data was fed into a **Lasso Regression** model for training and prediction.

---

### 🗺 Architecture Diagram

```
+------------------+       +------------------------------------------+       +-----------------------------+       +------------------------+
|    Raw Data      |  -->  | Feature Transformation                   |  -->  | One-Hot Encoding            |  -->  | Polynomial Features     |
| (train/test CSV) |       | (log, reciprocal, sqrt, cube_root)       |       | (categorical variables)     |       | (degree = 2)            |
+------------------+       +------------------------------------------+       +-----------------------------+       +------------------------+
                                                                                                                                |
                                                                                                                                v
                                                                                                     +------------------------+
                                                                                                     |  Standard Scaling      |
                                                                                                     |  (Normalization)       |
                                                                                                     +------------------------+
                                                                                                                                |
                                                                                                                                v
                                                                                                     +------------------------+
                                                                                                     |   Lasso Regression     |
                                                                                                     | (Training & Prediction)|
                                                                                                     +------------------------+
```

---

### 📝 Key Contributions

#### 🔹 Feature Engineering

* EDA revealed **Item Price** as a key driver of return volume.
* Created transformed variants of price using:

  * `log`, `sqrt`, `reciprocal`, `cube_root`
* Applied **Polynomial Features** and **StandardScaler** for non-linearity and normalization, improving accuracy.

#### 🔹 Categorical Encoding

* Used **One-Hot Encoding** on:

  * `Item_Type`, `Store_Type`, `Store_Location_Type`, `Store_Start_Year`
* Enabled the model to interpret categorical variables numerically and effectively.

#### 🔹 Model Evaluation

* Evaluated using **RMSE** on training and test sets.
* **Lasso Regression** consistently outperformed other models in cross-validation.

---

