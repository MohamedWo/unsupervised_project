# unsupervised_project

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Country Need Index for HELP International</title>
<style>
    body { font-family: Arial, sans-serif; line-height: 1.6; margin: 20px; }
    h1, h2, h3 { color: #2F4F4F; }
    table { border-collapse: collapse; width: 100%; margin-bottom: 20px; }
    th, td { border: 1px solid #ddd; padding: 8px; text-align: left; }
    th { background-color: #f2f2f2; }
    ul { margin-bottom: 20px; }
</style>
</head>
<body>

<h1>Country Need Index for HELP International</h1>

<h2>Overview</h2>
<p>
This project aims to <strong>categorize countries based on socio-economic and health indicators</strong> 
to help HELP International prioritize humanitarian aid. By analyzing factors such as child mortality, 
income, GDP per capita, health spending, and life expectancy, we generate a <strong>Need Score</strong> 
for each country.
</p>
<p>
The project uses <strong>unsupervised learning (clustering)</strong> to group countries and identify those in the direst need of aid.
</p>

<h2>Dataset</h2>
<p><strong>Country-data.csv</strong>: Contains socio-economic and health indicators for 167 countries.<br>
<strong>data-dictionary.csv</strong>: Description of each column in the dataset.</p>

<h3>Key columns:</h3>
<table>
<tr><th>Column</th><th>Description</th></tr>
<tr><td>country</td><td>Country name</td></tr>
<tr><td>child_mort</td><td>Child mortality (deaths per 1000 children under 5 years)</td></tr>
<tr><td>income</td><td>Net income per person</td></tr>
<tr><td>gdpp</td><td>GDP per capita</td></tr>
<tr><td>health</td><td>Total health spending per capita (%)</td></tr>
<tr><td>life_expec</td><td>Life expectancy at birth</td></tr>
<tr><td>exports</td><td>Exports per capita</td></tr>
<tr><td>imports</td><td>Imports per capita</td></tr>
<tr><td>inflation</td><td>Annual inflation rate</td></tr>
<tr><td>total_fer</td><td>Total fertility rate</td></tr>
</table>

<h2>Methodology</h2>
<ul>
<li><strong>Data Preprocessing:</strong> Checked for missing values (none found) and standardized numeric columns using <code>StandardScaler</code>.</li>
<li><strong>Feature Transformation:</strong> Columns where higher values indicate lower need (e.g., income, GDP, life expectancy) were inverted. Now, higher values = higher need.</li>
<li><strong>Need Score Calculation:</strong> Calculated a composite <strong>Need Score</strong> for each country by averaging standardized indicators. Sorted countries from highest to lowest score.</li>
<li><strong>Clustering (Optional):</strong> K-Means clustering can be applied to group countries with similar socio-economic profiles.</li>
</ul>

<h2>Top 15 Countries in Need</h2>
<table>
<tr><th>Country</th><th>Need Score</th></tr>
<tr><td>Nigeria</td><td>2.0117</td></tr>
<tr><td>Central African Republic</td><td>1.1987</td></tr>
<tr><td>Haiti</td><td>1.1388</td></tr>
<tr><td>Chad</td><td>1.0255</td></tr>
<tr><td>Mali</td><td>1.0066</td></tr>
<tr><td>Niger</td><td>0.9657</td></tr>
<tr><td>Angola</td><td>0.9601</td></tr>
<tr><td>Guinea</td><td>0.9211</td></tr>
<tr><td>Burkina Faso</td><td>0.9162</td></tr>
<tr><td>Eritrea</td><td>0.9120</td></tr>
<tr><td>Congo, Dem. Rep.</td><td>0.8956</td></tr>
<tr><td>Malawi</td><td>0.8904</td></tr>
<tr><td>Pakistan</td><td>0.8868</td></tr>
<tr><td>Zambia</td><td>0.8805</td></tr>
<tr><td>Sierra Leone</td><td>0.8658</td></tr>
</table>

<h2>Output</h2>
<p>
<strong>countries_need_ranking.csv</strong>: Contains all countries with their Need Scores and standardized socio-economic indicators, sorted from highest to lowest need.
</p>

<h2>Tools & Libraries</h2>
<ul>
<li>Python 3</li>
<li>Pandas</li>
<li>Scikit-learn (<code>StandardScaler</code>, <code>PCA</code>, <code>KMeans</code>)</li>
<li>Optional visualization: Matplotlib / Seaborn</li>
</ul>

<h2>How to Use</h2>
<ol>
<li>Download the dataset from Kaggle.</li>
<li>Run the notebook to generate the standardized features and Need Scores.</li>
<li>The resulting <code>countries_need_ranking.csv</code> can be used to:
    <ul>
        <li>Prioritize aid distribution.</li>
        <li>Visualize the countries by need.</li>
        <li>Apply clustering or further analysis.</li>
    </ul>
</li>
</ol>

<h2>Notes</h2>
<p>
- The methodology uses <strong>unsupervised learning</strong> and a simple composite index to quantify need.<br>
- The Need Score is <strong>relative</strong>, ranking countries compared to each other.
</p>

</body>
</html>
