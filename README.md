<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Conclusión Profesional - Estudio de Productividad Textil</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            padding: 40px 20px;
            line-height: 1.6;
        }

        .container {
            max-width: 1000px;
            margin: 0 auto;
            background: white;
            border-radius: 20px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.1);
            overflow: hidden;
        }

        .header {
            background: linear-gradient(135deg, #1e3c72 0%, #2a5298 100%);
            color: white;
            padding: 40px;
            text-align: center;
        }

        .header h1 {
            font-size: 28px;
            margin-bottom: 10px;
            font-weight: 600;
        }

        .header p {
            font-size: 14px;
            opacity: 0.9;
        }

        .content {
            padding: 40px;
        }

        .section {
            margin-bottom: 40px;
        }

        .section-title {
            font-size: 24px;
            font-weight: 600;
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 3px solid;
            display: inline-block;
        }

        .sweing-title {
            color: #2e7d32;
            border-bottom-color: #2e7d32;
        }

        .finishing-title {
            color: #c62828;
            border-bottom-color: #c62828;
        }

        .highlight-box {
            background: #f8f9fa;
            border-left: 4px solid;
            padding: 20px;
            margin: 20px 0;
            border-radius: 8px;
        }

        .success-box {
            border-left-color: #2e7d32;
            background: #e8f5e9;
        }

        .warning-box {
            border-left-color: #c62828;
            background: #ffebee;
        }

        .model-badge {
            display: inline-block;
            background: #e0e0e0;
            padding: 4px 12px;
            border-radius: 20px;
            font-size: 12px;
            font-weight: 600;
            margin-right: 10px;
        }

        .gbr-badge {
            background: #1976d2;
            color: white;
        }

        .nn-badge {
            background: #9c27b0;
            color: white;
        }

        .cause-list {
            list-style: none;
            padding-left: 20px;
            margin: 15px 0;
        }

        .cause-list li {
            margin: 10px 0;
            padding-left: 25px;
            position: relative;
        }

        .cause-list li:before {
            content: "⚠️";
            position: absolute;
            left: 0;
        }

        .conclusion-box {
            background: #e3f2fd;
            padding: 20px;
            border-radius: 12px;
            margin: 20px 0;
            border: 1px solid #bbdef5;
        }

        .conclusion-box strong {
            color: #1565c0;
        }

        hr {
            margin: 30px 0;
            border: none;
            height: 1px;
            background: linear-gradient(to right, transparent, #ccc, transparent);
        }

        .footer {
            background: #f8f9fa;
            padding: 20px 40px;
            text-align: center;
            font-size: 12px;
            color: #666;
            border-top: 1px solid #e0e0e0;
        }

        @media (max-width: 768px) {
            .content {
                padding: 20px;
            }
            .header h1 {
                font-size: 22px;
            }
            .section-title {
                font-size: 20px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>📌 Conclusión Profesional del Estudio</h1>
            <p>Modelado de Productividad Real en Planta Textil | Sweing vs Finishing</p>
        </div>

        <div class="content">
            <!-- Introducción -->
            <div class="section">
                <p style="margin-bottom: 15px; font-size: 16px; text-align: justify;">
                    El presente análisis tuvo como objetivo modelar la productividad real (<strong>actual_productivity</strong>) 
                    en dos departamentos clave de una planta textil: <strong>Sweing</strong> (costura) y <strong>Finishing</strong> (acabado). 
                    Se implementaron y compararon dos enfoques de machine learning —<strong>Gradient Boosting Regressor (GBR)</strong> 
                    y <strong>Redes Neuronales (NN)</strong>— con el fin de identificar el modelo más adecuado para cada área operativa.
                </p>
            </div>

            <!-- Departamento Sweing -->
            <div class="section">
                <h2 class="section-title sweing-title">🧵 Departamento de Sweing (Costura)</h2>
                
                <p style="margin: 20px 0 15px 0; text-align: justify;">
                    Los resultados obtenidos en el departamento de Sweing fueron <strong>altamente satisfactorios</strong>. 
                    Ambos modelos lograron capturar eficazmente la variabilidad subyacente de los datos, evidenciado por 
                    métricas de desempeño sólidas y estables:
                </p>

                <div class="highlight-box">
                    <p><span class="model-badge gbr-badge">GBR</span> 
                    <strong>Gradient Boosting Regressor</strong> demostró un excelente equilibrio entre sesgo y varianza, 
                    con alta capacidad predictiva y buena generalización.</p>
                    
                    <p style="margin-top: 15px;"><span class="model-badge nn-badge">NN</span> 
                    <strong>Red Neuronal</strong> también alcanzó un rendimiento competitivo, aunque con una ligera mayor 
                    sensibilidad a la configuración de hiperparámetros y al preprocesamiento.</p>
                </div>

                <div class="conclusion-box">
                    ✅ <strong>Conclusión para Sweing:</strong> Los datos presentan una <strong>alta calidad y señal predictiva</strong>. 
                    Cualquiera de los dos modelos es viable, recomendándose el uso de <strong>GBR por su interpretabilidad 
                    y robustez</strong> en entornos de producción, o bien un <strong>modelo ensemble</strong> para maximizar 
                    el rendimiento.
                </div>
            </div>

            <!-- Departamento Finishing -->
            <div class="section">
                <h2 class="section-title finishing-title">🧷 Departamento de Finishing (Acabado)</h2>
                
                <p style="margin: 20px 0 15px 0; text-align: justify;">
                    Por el contrario, el departamento de Finishing presentó <strong>limitaciones estructurales significativas</strong>. 
                    A pesar de aplicar técnicas avanzadas de preprocesamiento, ingeniería de características y optimización 
                    mediante <code>GridSearchCV</code>, ningún modelo logró capturar relaciones relevantes entre las variables 
                    disponibles y la productividad real.
                </p>

                <p><strong>Las posibles causas identificadas incluyen:</strong></p>
                <ul class="cause-list">
                    <li><strong>Baja variabilidad</strong> en las variables predictoras (ej. <code>incentive</code> prácticamente constante en cero).</li>
                    <li><strong>Alta proporción de ruido</strong> con respecto a la señal útil.</li>
                    <li><strong>Posible falta de variables críticas</strong> no registradas en el conjunto de datos original 
                        (ej. eficiencia individual del operario, tiempos de espera no documentados, calidad del material).</li>
                </ul>

                <div class="conclusion-box" style="background: #ffebee; border-color: #c62828;">
                    ⚠️ <strong>Conclusión para Finishing:</strong> Los datos disponibles son <strong>insuficientes o inadecuados</strong> 
                    para construir un modelo predictivo confiable. Se recomienda <strong>no implementar</strong> ninguno de los modelos 
                    evaluados en este departamento hasta contar con un <strong>rediseño del sistema de captura de datos operacionales</strong>.
                </div>
            </div>

            <!-- Resumen visual -->
            <hr>

            <div style="display: flex; flex-wrap: wrap; gap: 20px; justify-content: space-between; margin-top: 20px;">
                <div style="flex: 1; min-width: 200px; background: #e8f5e9; padding: 20px; border-radius: 12px; text-align: center;">
                    <div style="font-size: 40px;">✅</div>
                    <h3 style="color: #2e7d32; margin: 10px 0;">Sweing</h3>
                    <p style="font-size: 14px;">Datos de alta calidad<br>Modelos predictivos exitosos<br>R² > 0.7</p>
                </div>
                <div style="flex: 1; min-width: 200px; background: #ffebee; padding: 20px; border-radius: 12px; text-align: center;">
                    <div style="font-size: 40px;">⚠️</div>
                    <h3 style="color: #c62828; margin: 10px 0;">Finishing</h3>
                    <p style="font-size: 14px;">Limitaciones estructurales<br>Sin capacidad predictiva<br>Requiere rediseño de datos</p>
                </div>
                <div style="flex: 1; min-width: 200px; background: #e3f2fd; padding: 20px; border-radius: 12px; text-align: center;">
                    <div style="font-size: 40px;">🎯</div>
                    <h3 style="color: #1565c0; margin: 10px 0;">Recomendación</h3>
                    <p style="font-size: 14px;">Implementar GBR en Sweing<br>Auditoría de datos en Finishing<br>Ensemble opcional</p>
                </div>
            </div>
        </div>

        <div class="footer">
            <p>Estudio de Machine Learning aplicado a productividad textil | Modelos evaluados: Gradient Boosting Regressor & Redes Neuronales</p>
            <p style="margin-top: 5px;">📊 Datos procesados con Python, scikit-learn, TensorFlow y pandas</p>
        </div>
    </div>
</body>
</html>
