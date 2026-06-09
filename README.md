# telco-churn-real-time-prediction

## Project Overview
This repository contains an end-to-end Machine Learning pipeline designed to predict customer churn in the telecommunications industry. The primary objective is to build a **Low-Latency, Real-Time Prediction Model** that not only accurately identifies at-risk customers but also maintains **100% interpretability** for the business and retention teams.

## Project Architecture & Lifecycle
The project is modularized into 5 sequential Jupyter Notebooks, simulating a professional Data Science lifecycle:

*   **`1-Data-understanding.ipynb`**: Exploratory Data Analysis (EDA), univariate/bivariate analysis, and identifying class imbalance & business behavioral biases.
*   **`2-Data-cleaning.ipynb`**: Handling hidden missing values (e.g., type mismatch in `TotalCharges`), duplicate removal, and ensuring data consistency for stable real-time inference.
*   **`3-Data-transformation.ipynb`**: Scaling numerical features, encoding categorical variables, and ensuring appropriate data distributions.
*   **`4-Feature-engineering.ipynb`**: Creating derived business-centric features to boost model precision without adding computational overhead.
*   **`5-Feature-selection.ipynb`**: The core technical analysis comparing **Principal Component Analysis (PCA)** vs. **Embedded Feature Selection (Lasso L1 Regularization)**.

## Key Technical Highlight: PCA vs. Lasso L1
A major constraint of this project was balancing **model performance (latency/precision)** with **business transparency (interpretability)**.

*   **The PCA Approach:** While PCA successfully compressed the dataset and maintained 95% variance, it was **rejected** for the final production model. The transformation into principal components (PC1, PC2) destroyed the interpretability of the features, making it impossible for the marketing team to know *why* a customer was churning.
*   **The Lasso L1 Approach (Selected):** Lasso regularization was applied to perform strict feature selection. It effectively zeroed out noisy features, reducing dimensionality while keeping the original, understandable business features intact (e.g., `Tenure`, `MonthlyCharges`, `Contract_Type`). 

**Conclusion:** Lasso L1 provided the optimal architecture, achieving a lightweight model for real-time inference while allowing retention teams to act on specific churn drivers.

## Business Value & Results
*   **Precision Focus:** The model prioritizes precision to ensure that retention budgets (discounts, offers) are not wasted on False Positives (customers who were not actually going to churn).
*   **Actionable Insights:** By avoiding "black-box" dimensionality reduction, the output directly informs the business whether a customer is leaving due to high monthly charges or early-tenure dissatisfaction.

## 🛠️ Tech Stack
*   **Language:** Python (Pandas, NumPy)
*   **Machine Learning:** Scikit-Learn (Logistic Regression, PCA, Lasso L1)
*   **Data Visualization:** Matplotlib, Seaborn

## ⚙️ How to Run
1. Clone the repository.
2. Ensure `telco-churn.csv` is in the root directory.
3. Run the Jupyter Notebooks sequentially from `1` to `5` to reproduce the data pipeline and final model evaluation.
