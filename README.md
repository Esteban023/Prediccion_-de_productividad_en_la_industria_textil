# Textile Productivity Prediction using Machine Learning

## Overview

This project focuses on predicting **worker productivity** in a textile manufacturing environment using supervised Machine Learning techniques.

The goal is not only to build predictive models, but also to evaluate how **data quality and feature relevance** impact model performance across different operational areas.

A key aspect of this project is the **separate analysis by department**, allowing us to identify structural differences in the data and their impact on predictive capability.

---

## Problem Statement

The objective is to predict `actual_productivity`, a continuous variable representing the real efficiency of workers in a production setting.

This is framed as a **regression problem**, where productivity is estimated based on operational features such as:

* department
* incentives
* working conditions
* workload and scheduling variables

---

## Dataset

The dataset is sourced from the UCI Machine Learning Repository:

https://archive.ics.uci.edu/ml/datasets/Productivity+Prediction+of+Garment+Employees

It includes:

* ~1200 observations
* multiple operational features
* target variable: `actual_productivity`

The analysis is performed separately for:

* **Sewing** (listed as `sweing` in the dataset)
* **Finishing**

---

## Methodology

### Data Preprocessing

* Missing value imputation
* Outlier handling
* Encoding of categorical variables
* Feature scaling

### Feature Engineering

Derived features were created to better capture operational dynamics, including:

* theoretical productivity
* workload per worker
* incentive ratios
* time per worker
* style change rates

### Models Implemented

* Linear Regression (baseline)
* Random Forest Regressor
* Gradient Boosting Regressor

---

## Model Evaluation

Models were evaluated using:

* R² Score
* Mean Absolute Error (MAE)
* Root Mean Squared Error (RMSE)

---

## Results

| Department | Model             | R²     | MAE    | RMSE   |
| ---------- | ----------------- | ------ | ------ | ------ |
| Finishing  | Random Forest     | 0.3220 | 0.1130 | 0.1506 |
| Finishing  | Gradient Boosting | 0.2872 | 0.1155 | 0.1544 |
| Finishing  | Linear Regression | 0.2753 | 0.1241 | 0.1557 |
| Sewing     | Gradient Boosting | 0.8448 | 0.0349 | 0.0568 |
| Sewing     | Random Forest     | 0.8433 | 0.0331 | 0.0571 |
| Sewing     | Linear Regression | 0.7948 | 0.0448 | 0.0653 |

### Key Observations

* The **Sewing department** shows strong predictive performance, with Gradient Boosting achieving an R² of 0.8448
* The **Finishing department** shows weaker performance, with the best model reaching 0.3220 R²
* This indicates that predictive performance is strongly dependent on **data quality and feature variability**

---

## Visual Analysis

### Predicted vs Actual (Sewing)

![Sewing Predicted vs Actual](images/sewing_predicted_vs_actual.png)

### Predicted vs Actual (Finishing)

![Finishing Predicted vs Actual](images/finishing_predicted_vs_actual.png)

### Residual Analysis (Sewing)

![Sewing Residuals](images/sewing_residuals.png)

### Residual Analysis (Finishing)

![Finishing Residuals](images/finishing_residuals.png)

### Feature Importance (Sewing)

![Feature Importance Sewing](images/sewing_feature_importance.png)

### Feature Importance (Finishing)

![Feature Importance Finishing](images/finishing_feature_importance.png)

### Finishing Productivity Distribution

![Finishing Distribution](images/finishing_distribution.png)

---

## Explainability

SHAP (SHapley Additive exPlanations) was used to interpret model behavior and identify key drivers of productivity.

### SHAP Summary (Sewing)

![SHAP Summary](images/sewing_shap_summary.png)

---

## Key Insights

* Model performance depends heavily on **data quality**
* The Sewing department contains strong predictive signals
* The Finishing department lacks sufficient variability for accurate prediction
* Not all business problems are solvable with Machine Learning if the data is not suitable

---

## Limitations

* Limited feature variability in certain departments
* Missing operational variables (e.g., worker-level efficiency)
* Dataset constraints impact model performance

---

## Future Work

* Add more operational features
* Explore advanced ensemble methods
* Improve data collection
* Deploy the model as an API

---

## Project Structure

data/
notebooks/
images/
models/
model_results.csv

---

## How to Run

pip install -r requirements.txt

Run the notebook in Google Colab or locally.

---

## Tech Stack

* Python
* Pandas, NumPy
* Scikit-learn
* SHAP
* Matplotlib

---

Here is the conclusion with the Sweing summary translated to English:

---

<h1>📌 Conclusión Profesional del Estudio</h1>
<p>
The present analysis aimed to model the actual productivity (<strong>actual_productivity</strong>)
in two key departments of a textile plant: <strong>Sweing</strong> and <strong>Finishing</strong>.
Two machine learning approaches will be implemented and compared: <strong>Gradient Boosting Regressor (GBR)</strong> and <strong>Neural Networks (NN)</strong>—in order to identify the most suitable model for each operational area.
</p>
<hr>
<h2>🧵 Departamento de Sweing (Costura)</h2>
<p>
The results obtained in the Sweing department were <strong>highly satisfactory</strong>.
Both models effectively captured the underlying variability of the data, as evidenced by
strong and stable performance metrics:
</p>
<p>
<strong>Gradient Boosting Regressor</strong> demonstrated an excellent balance between bias and variance,
with high predictive capacity and good generalization.
</p>
<p>
<strong>Neural Network</strong> also achieved competitive performance, although with slightly greater
sensitivity to hyperparameter configuration and preprocessing.
</p>
<p>
✅ <strong>Conclusion for Sweing:</strong> The data presents <strong>high quality and predictive signal</strong>.
Either model is viable; the use of <strong>GBR is recommended for its interpretability
and robustness</strong> in production environments, or alternatively an <strong>ensemble model</strong> to maximize
performance.
</p>
<hr>
<h2>🧷 Departamento de Finishing (Acabado)</h2>
<p>
In contrast, the Finishing department presented <strong>significant structural limitations</strong>.
Despite applying advanced preprocessing techniques, feature engineering, and optimization
via <code>GridSearchCV</code>, no model was able to capture relevant relationships between the available
variables and actual productivity.
</p>
<p><strong>The possible causes identified include:</strong></p>
<ul>
    <li><strong>Low variability</strong> in predictor variables (e.g. <code>incentive</code> practically constant at zero).</li>
    <li><strong>High proportion of noise</strong> relative to the useful signal.</li>
    <li><strong>Possible lack of critical variables</strong> not recorded in the original dataset
        (e.g. individual operator efficiency, undocumented waiting times, material quality).</li>
</ul>
<p>
⚠️ <strong>Conclusion for Finishing:</strong> The available data is <strong>insufficient or inadequate</strong>
to build a reliable predictive model. It is recommended <strong>not to deploy</strong> any of the evaluated models in this department until a <strong>redesign of the operational data capture system</strong> is in place.
</p>
<hr>
<h3>📊 Executive Summary</h3>
<p>
<strong>Sweing:</strong> High-quality data. Successful predictive models (R² > 0.7). Recommendation: Deploy GBR in production.<br>
<strong>Finishing:</strong> Limitaciones estructurales. Sin capacidad predictiva. Recomendación: Auditoría y rediseño del sistema de captura de datos.
</p>

</body>
</html>
