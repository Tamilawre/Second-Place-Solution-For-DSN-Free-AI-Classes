### 🥈 Second place solution for the DSN Free AI Classes in Every City 2025 Hackathon

This project was developed for a challenge hosted by Zindi using Google Colab. The goal was to build a regression-based solution aimed at providing insights into which products yield higher returns at **Impact Stores**, a Nigerian retail chain with over 1,500 products. The insights are intended to guide strategic expansion decisions.

### Core Objective: 🔍
The core objective was to predict **item store returns** using machine learning regression models. After extensive model experimentation and cross-validation on various algorithms—including Ridge Regression, Lasso Regression, Support Vector Regressor (SVR), Decision Trees, and Linear Regression—I found **Lasso Regression** with an alpha value of **60.5** to yield the best performance based on **Root Mean Squared Error (RMSE)**.

### 🔄 ETL Pipeline
📥 **Extract**
- Loaded raw train.csv and test.csv files containing customer, product, and order features.

🔧 **Transform**
- Applied mathematical transformations: log, reciprocal, sqrt, cube_root (to reduce skew).

- Encoded categorical features using One-Hot Encoding.

- Generated polynomial features (degree = 2) to capture non-linear relationships.

- Normalized all features using StandardScaler.

📤 **Load**
- Transformed data was fed into a Lasso Regression model for training and prediction.

#### Key Contributions: 📝

* **Feature Engineering**:
  Exploratory Data Analysis (EDA) revealed that **Item Price** played a critical role in predicting returns. To enrich the feature space, I created transformed versions of the price feature using **logarithmic, square root, reciprocal**, and **cube root** functions. I also utilised Polynomial Features to capture non-linearity and the Standard Scalar function to normalise input features. These transformations contributed to improved model accuracy.

* **Categorical Encoding**:
  I applied **one-hot encoding** to categorical variables(Item_Type, Store_Type, Store_Location_Type, Store_Start_Year), which further boosted performance by allowing the model to interpret non-numeric data effectively.

* **Model Evaluation**:
  Performance was assessed using **RMSE** on both the training and test sets to ensure the model generalizes well. Lasso Regression consistently outperformed other models in cross-validation, making it the final choice.

### Architecture Diagram 🗺
<pre lang="markdown"> ``` +------------------+       +----------------------------------------+       +-----------------------------+       +------------------------+
      |    Raw Data      |  -->  | Feature Transformation                 |  -->  | One-Hot Encoding            |  -->  | Polynomial Features     |
      | (train/test CSV) |       | (log, reciprocal, sqrt, cube_root)     |       | (Categorical Variables)     |       | (degree = 2)            |
      +------------------+       +----------------------------------------+       +-----------------------------+       +------------------------+
                                                                                                                                    |
                                                                                                                                    v
                                                                                                                         +------------------------+
                                                                                                                         | Standard Scaling       |
                                                                                                                         | (Normalization)        |
                                                                                                                         +------------------------+
                                                                                                                                    |
                                                                                                                                    v
                                                                                                                         +------------------------+
                                                                                                                         |  Lasso Regression      |
                                                                                                                         |  (Training & Prediction)|
                                                                                                                         +------------------------+
                ``` </pre>
                        



