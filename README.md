<h1>Textile Productivity Prediction using Machine Learning</h1>

<h2>Overview</h2>

<p>This project focuses on predicting <strong>worker productivity</strong> in a textile manufacturing environment using supervised Machine Learning techniques.</p>

<p>The goal is not only to build predictive models, but also to evaluate how <strong>data quality and feature relevance</strong> impact model performance across different operational areas.</p>

<p>A key aspect of this project is the <strong>separate analysis by department</strong>, allowing us to identify structural differences in the data and their impact on predictive capability.</p>

<hr />

<h2>Problem Statement</h2>

<p>The objective is to predict <code>actual_productivity</code>, a continuous variable representing the real efficiency of workers in a production setting.</p>

<p>This is framed as a <strong>regression problem</strong>, where productivity is estimated based on operational features such as:</p>

<ul>
<li>department</li>
<li>incentives</li>
<li>working conditions</li>
<li>workload and scheduling variables</li>
</ul>

<hr />

<h2>Dataset</h2>

<p>The dataset is sourced from the UCI Machine Learning Repository:</p>

<p><a href="https://archive.ics.uci.edu/ml/datasets/Productivity+Prediction+of+Garment+Employees">https://archive.ics.uci.edu/ml/datasets/Productivity+Prediction+of+Garment+Employees</a></p>

<p>It includes:</p>

<ul>
<li>~1200 observations</li>
<li>multiple operational features</li>
<li>target variable: <code>actual_productivity</code></li>
</ul>

<p>The analysis is performed separately for:</p>

<ul>
<li><strong>Sewing</strong> (listed as <code>sweing</code> in the dataset)</li>
<li><strong>Finishing</strong></li>
</ul>

<hr />

<h2>Methodology</h2>

<h3>Data Preprocessing</h3>

<ul>
<li>Missing value imputation</li>
<li>Outlier handling</li>
<li>Encoding of categorical variables</li>
<li>Feature scaling</li>
</ul>

<h3>Feature Engineering</h3>

<p>Derived features were created to better capture operational dynamics, including:</p>

<ul>
<li>theoretical productivity</li>
<li>workload per worker</li>
<li>incentive ratios</li>
<li>time per worker</li>
<li>style change rates</li>
</ul>

<h3>Models Implemented</h3>

<ul>
<li>Linear Regression (baseline)</li>
<li>Random Forest Regressor</li>
<li>Gradient Boosting Regressor</li>
</ul>

<hr />

<h2>Model Evaluation</h2>

<p>Models were evaluated using:</p>

<ul>
<li>R² Score</li>
<li>Mean Absolute Error (MAE)</li>
<li>Root Mean Squared Error (RMSE)</li>
</ul>

<hr />

<h2>Results</h2>

<table>
<thead>
<tr>
<th>Department</th>
<th>Model</th>
<th>R²</th>
<th>MAE</th>
<th>RMSE</th>
</tr>
</thead>
<tbody>
<tr>
<td>Finishing</td>
<td>Random Forest</td>
<td>0.3220</td>
<td>0.1130</td>
<td>0.1506</td>
</tr>
<tr>
<td>Finishing</td>
<td>Gradient Boosting</td>
<td>0.2872</td>
<td>0.1155</td>
<td>0.1544</td>
</tr>
<tr>
<td>Finishing</td>
<td>Linear Regression</td>
<td>0.2753</td>
<td>0.1241</td>
<td>0.1557</td>
</tr>
<tr>
<td>Sweing</td>
<td>Gradient Boosting</td>
<td>0.8448</td>
<td>0.0349</td>
<td>0.0568</td>
</tr>
<tr>
<td>Sweing</td>
<td>Random Forest</td>
<td>0.8433</td>
<td>0.0331</td>
<td>0.0571</td>
</tr>
<tr>
<td>Sweing</td>
<td>Linear Regression</td>
<td>0.7948</td>
<td>0.0448</td>
<td>0.0653</td>
</tr>
</tbody>
</table>

<h3>Key Observations</h3>

<ul>
<li>The <strong>Sweing department</strong> shows strong predictive performance, with Gradient Boosting achieving an R² of 0.8448</li>
<li>The <strong>Finishing department</strong> shows weaker performance, with the best model reaching 0.3220 R²</li>
<li>This indicates that predictive performance is strongly dependent on <strong>data quality and feature variability</strong></li>
</ul>

<hr />

<h2>Visual Analysis</h2>

<h3>Predicted vs Actual (Sewing)</h3>

<p><img src="images/sewing_predicted_vs_actual.png" alt="Sewing Predicted vs Actual" /></p>

<h3>Predicted vs Actual (Finishing)</h3>

<p><img src="images/finishing_predicted_vs_actual.png" alt="Finishing Predicted vs Actual" /></p>

<h3>Residual Analysis (Sewing)</h3>

<p><img src="images/sewing_residuals.png" alt="Sewing Residuals" /></p>

<h3>Residual Analysis (Finishing)</h3>

<p><img src="images/finishing_residuals.png" alt="Finishing Residuals" /></p>

<h3>Feature Importance (Sewing)</h3>

<p><img src="images/sewing_feature_importance.png" alt="Feature Importance Sewing" /></p>

<h3>Feature Importance (Finishing)</h3>

<p><img src="images/finishing_feature_importance.png" alt="Feature Importance Finishing" /></p>

<h3>Finishing Productivity Distribution</h3>

<p><img src="images/finishing_distribution.png" alt="Finishing Distribution" /></p>

<hr />

<h2>Explainability</h2>

<p>SHAP (SHapley Additive exPlanations) was used to interpret model behavior and identify key drivers of productivity.</p>

<h3>SHAP Summary (Sewing)</h3>

<p><img src="images/sewing_shap_summary.png" alt="SHAP Summary" /></p>

<hr />

<h2>Key Insights</h2>

<ul>
<li>Model performance depends heavily on <strong>data quality</strong></li>
<li>The Sewing department contains strong predictive signals</li>
<li>The Finishing department lacks sufficient variability for accurate prediction</li>
<li>Not all business problems are solvable with Machine Learning if the data is not suitable</li>
</ul>

<hr />

<h2>Limitations</h2>

<ul>
<li>Limited feature variability in certain departments</li>
<li>Missing operational variables (e.g., worker-level efficiency)</li>
<li>Dataset constraints impact model performance</li>
</ul>

<hr />

<h2>Future Work</h2>

<ul>
<li>Add more operational features</li>
<li>Explore advanced ensemble methods</li>
<li>Improve data collection</li>
<li>Deploy the model as an API</li>
</ul>

<hr />

<h2>Project Structure</h2>

<pre><code>data/
notebooks/
images/
models/
model_results.csv
</code></pre>

<hr />

<h2>How to Run</h2>

<pre><code>pip install -r requirements.txt
</code></pre>

<p>Run the notebook in Google Colab or locally.</p>

<hr />

<h2>Tech Stack</h2>

<ul>
<li>Python</li>
<li>Pandas, NumPy</li>
<li>Scikit-learn</li>
<li>SHAP</li>
<li>Matplotlib</li>
</ul>

<hr />

<h2>📌 Conclusion</h2>

<p>The analysis confirms that the Sewing department yields robust predictive performance (R² up to 0.8448 with Gradient Boosting), driven by meaningful operational signals and adequate feature variability. In contrast, the Finishing department shows limited predictability (best R² 0.3220), highlighting that data quality and feature richness are critical for successful machine learning applications. These findings underscore that not every business problem is equally solvable with ML; domain-specific data assessments are essential before deploying predictive models.</p>



