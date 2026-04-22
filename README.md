📌 Conclusión Profesional del Estudio
El presente análisis tuvo como objetivo modelar la productividad real (actual_productivity) en dos departamentos clave de una planta textil: Sweing (costura) y Finishing (acabado). Se implementaron y compararon dos enfoques de machine learning —Gradient Boosting Regressor (GBR) y Redes Neuronales (NN)— con el fin de identificar el modelo más adecuado para cada área operativa.

🧵 Departamento de Sweing (Costura)
Los resultados obtenidos en el departamento de Sweing fueron altamente satisfactorios. Ambos modelos lograron capturar eficazmente la variabilidad subyacente de los datos, evidenciado por métricas de desempeño sólidas y estables:

Gradient Boosting Regressor demostró un excelente equilibrio entre sesgo y varianza, con alta capacidad predictiva y buena generalización.

Red Neuronal también alcanzó un rendimiento competitivo, aunque con una ligera mayor sensibilidad a la configuración de hiperparámetros y al preprocesamiento.

✅ Conclusión para Sweing: Los datos presentan una alta calidad y señal predictiva. Cualquiera de los dos modelos es viable, recomendándose el uso de GBR por su interpretabilidad y robustez en entornos de producción, o bien un modelo ensemble para maximizar el rendimiento.

🧷 Departamento de Finishing (Acabado)
Por el contrario, el departamento de Finishing presentó limitaciones estructurales significativas. A pesar de aplicar técnicas avanzadas de preprocesamiento, ingeniería de características y optimización mediante GridSearchCV, ningún modelo logró capturar relaciones relevantes entre las variables disponibles y la productividad real.

Las posibles causas identificadas incluyen:

Baja variabilidad en las variables predictoras (ej. incentive prácticamente constante en cero).

Alta proporción de ruido con respecto a la señal útil.

Posible falta de variables críticas no registradas en el conjunto de datos original (ej. eficiencia individual del operario, tiempos de espera no documentados, calidad del material).

⚠️ Conclusión para Finishing: Los datos disponibles son insuficientes o inadecuados para construir un modelo predictivo confiable. Se recomienda no implementar ninguno de los modelos evaluados en este departamento hasta contar con un rediseño del sistema de captura de datos operacionales.

