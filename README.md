# Real-Time Customer Churn Prediction Pipeline

A production-oriented machine learning pipeline for predicting customer churn in the telecommunications industry under real-time inference constraints.

## Project Goal

The objective of this project was not only to maximize predictive performance, but also to balance:

* Low-latency real-time inference
* Business interpretability
* Feature efficiency
* Retention-focused decision making

The final solution was designed to support customer retention teams by identifying high-risk customers while preserving explainable business drivers.

---

## Key Results

| Model                        | Accuracy | Precision | Recall | F1-Score |
| ---------------------------- | -------- | --------- | ------ | -------- |
| Baseline (All Features)      | 0.8013   | 0.6546    | 0.5321 | 0.5870   |
| Lasso L1 (Selected Features) | 0.7991   | 0.6502    | 0.5267 | 0.5820   |
| PCA (95% Variance)           | 0.7963   | 0.6455    | 0.5160 | 0.5736   |

### Final Decision

Lasso L1 was selected as the production-ready solution because it achieved near-baseline performance while preserving full feature interpretability and reducing model complexity.

---

## Project Highlights

* Built an end-to-end machine learning pipeline following the CRISP-DM framework.
* Handled hidden missing values and data quality issues.
* Performed feature engineering using domain-driven customer behavior indicators.
* Evaluated PCA and Lasso L1 dimensionality reduction techniques.
* Optimized the solution for low-latency real-time deployment scenarios.
* Preserved business transparency for retention and marketing teams.

---

## Repository Structure

1-Data-understanding.ipynb

2-Data-cleaning.ipynb

3-Data-transformation.ipynb

4-Feature-engineering.ipynb

5-Feature-selection.ipynb

---

## Technology Stack

* Python
* Pandas
* NumPy
* Scikit-Learn
* Matplotlib
* Seaborn

---

## Business Impact

The model identifies customers likely to churn and provides interpretable signals that enable proactive retention strategies.

Unlike PCA-based approaches, the final model preserves original business features, allowing stakeholders to understand the factors driving customer churn.
