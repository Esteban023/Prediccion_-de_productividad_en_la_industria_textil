# Prediccion_-de_productividad_en_la_industria_textil
Este script implementa un pipeline completo de Machine Learning para predecir la productividad real (actual_productivity) de trabajadores en la industria textil, utilizando datos operativos de producción.

⚙️ Flujo general del sistema
1. Carga y preparación de datos
Se carga el dataset garments_worker_productivity.csv.
Se divide el problema en dos subconjuntos:
Sewing (costura)
Finishing (acabado)

Cada uno tiene su propio proceso de feature engineering.

2. Feature Engineering (Ingeniería de características)

Se crean variables derivadas relevantes para mejorar el poder predictivo:

Ejemplos:
theoretical_productivity: productividad esperada teórica.
incentive_ratio: relación incentivo / horas extra.
workload_per_worker: carga de trabajo por trabajador.
workers_overtime_interaction: interacción entre trabajadores y horas extra.

Además:
Conversión de fechas a formato numérico (ordinal_date).
Limpieza de datos (NaN, columnas irrelevantes).
3. Preprocesamiento

Se usa un pipeline de sklearn:

Numéricas:
Imputación con mediana
Escalado robusto (RobustScaler)
Categóricas:
Imputación por moda
One-Hot Encoding

Esto asegura consistencia y evita data leakage.

4. Eliminación de outliers

Se aplica:

IsolationForest

Para:

Reducir ruido
Mejorar la generalización del modelo
5. Modelado

Se implementan dos enfoques:

🌳 Modelo basado en árboles
GradientBoostingRegressor
Optimizado con GridSearchCV (para finishing)
🧠 Red neuronal (solo sewing)
Arquitectura:
Capas densas (64 → 32 → 16 → 1)
Batch Normalization
Regularización L2
Función de pérdida: Huber
Métrica: R²
Callbacks:
EarlyStopping
ReduceLROnPlateau
ModelCheckpoint
6. Evaluación

Se utilizan métricas:

R² (coeficiente de determinación)
MSE (error cuadrático medio)

Se comparan:

Entrenamiento vs test
Modelos: Gradient Boosting vs Red Neuronal
7. Visualización
Curvas de entrenamiento:
Loss
R²
Comparación de predicciones vs valores reales
