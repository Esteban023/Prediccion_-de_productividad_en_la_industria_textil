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

## Conclusion

This project demonstrates how to build and evaluate predictive models while also identifying when Machine Learning is limited by data quality.

Understanding these limitations is critical when applying ML to real-world problems.


<h1>📌 Conclusión Profesional del Estudio</h1>

<p>
El presente análisis tuvo como objetivo modelar la productividad real (<strong>actual_productivity</strong>) 
en dos departamentos clave de una planta textil: <strong>Sweing</strong> (costura) y <strong>Finishing</strong> (acabado). 
Se implementaron y compararon dos enfoques de machine learning —<strong>Gradient Boosting Regressor (GBR)</strong> 
y <strong>Redes Neuronales (NN)</strong>— con el fin de identificar el modelo más adecuado para cada área operativa.
</p>

<hr>

<h2>🧵 Departamento de Sweing (Costura)</h2>

<p>
Los resultados obtenidos en el departamento de Sweing fueron <strong>altamente satisfactorios</strong>. 
Ambos modelos lograron capturar eficazmente la variabilidad subyacente de los datos, evidenciado por 
métricas de desempeño sólidas y estables:
</p>

<p>
<strong>Gradient Boosting Regressor</strong> demostró un excelente equilibrio entre sesgo y varianza, 
con alta capacidad predictiva y buena generalización.
</p>

<p>
<strong>Red Neuronal</strong> también alcanzó un rendimiento competitivo, aunque con una ligera mayor 
sensibilidad a la configuración de hiperparámetros y al preprocesamiento.
</p>

<p>
✅ <strong>Conclusión para Sweing:</strong> Los datos presentan una <strong>alta calidad y señal predictiva</strong>. 
Cualquiera de los dos modelos es viable, recomendándose el uso de <strong>GBR por su interpretabilidad 
y robustez</strong> en entornos de producción, o bien un <strong>modelo ensemble</strong> para maximizar 
el rendimiento.
</p>

<hr>

<h2>🧷 Departamento de Finishing (Acabado)</h2>

<p>
Por el contrario, el departamento de Finishing presentó <strong>limitaciones estructurales significativas</strong>. 
A pesar de aplicar técnicas avanzadas de preprocesamiento, ingeniería de características y optimización 
mediante <code>GridSearchCV</code>, ningún modelo logró capturar relaciones relevantes entre las variables 
disponibles y la productividad real.
</p>

<p><strong>Las posibles causas identificadas incluyen:</strong></p>

<ul>
    <li><strong>Baja variabilidad</strong> en las variables predictoras (ej. <code>incentive</code> prácticamente constante en cero).</li>
    <li><strong>Alta proporción de ruido</strong> con respecto a la señal útil.</li>
    <li><strong>Posible falta de variables críticas</strong> no registradas en el conjunto de datos original 
        (ej. eficiencia individual del operario, tiempos de espera no documentados, calidad del material).</li>
</ul>

<p>
⚠️ <strong>Conclusión para Finishing:</strong> Los datos disponibles son <strong>insuficientes o inadecuados</strong> 
para construir un modelo predictivo confiable. Se recomienda <strong>no implementar</strong> ninguno de los modelos 
evaluados en este departamento hasta contar con un <strong>rediseño del sistema de captura de datos operacionales</strong>.
</p>

<hr>

<h3>📊 Resumen Ejecutivo</h3>

<p>
<strong>Sweing:</strong> Datos de alta calidad. Modelos predictivos exitosos (R² > 0.7). Recomendación: Implementar GBR en producción.<br>
<strong>Finishing:</strong> Limitaciones estructurales. Sin capacidad predictiva. Recomendación: Auditoría y rediseño del sistema de captura de datos.
</p>

</body>
</html>
