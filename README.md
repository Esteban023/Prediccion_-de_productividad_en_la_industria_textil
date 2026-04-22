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
