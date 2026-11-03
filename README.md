# Air Pollution Clustering with K-Means

**Unsupervised machine learning | Python | Scikit-learn | Exploratory data analysis**

## Overview
This project explores patterns in air-pollution measurements using K-Means clustering. Five pollutant variables: SO2, NO2, O3, PM2.5 and PM10, are standardised and grouped into three clusters. Exploratory analysis, cluster selection diagnostics and PCA visualisation help describe the differences between the groups.

## Data
The notebook's saved output reports 3,347 records and five numeric pollutant variables, with no missing values in those columns. Consequently, these clusters should not be treated as validated geographic or public-health classifications.

To reproduce the analysis, obtain the original authorised dataset and place `airpoll.csv` in the repository root.

## Methods
1. Inspect data types, summary statistics, distributions, outliers and correlations.
2. Standardise the five variables using `StandardScaler`.
3. Compare candidate cluster counts using the elbow method and silhouette scores.
4. Fit `KMeans(n_clusters=3, random_state=42, n_init=10)`.
5. Summarise cluster sizes and mean pollutant levels.
6. Project standardised data to two principal components for a 2D plot and visualise cluster profiles.

## Saved results

| Cluster | Records | SO2 | NO2 | O3 | PM2.5 | PM10 |
|---|---:|---:|---:|---:|---:|---:|
| 0 | 531 | 23.65 | 45.76 | 39.39 | 48.59 | 83.96 |
| 1 | 1,312 | 10.67 | 23.39 | 57.89 | 22.97 | 39.15 |
| 2 | 1,504 | 16.75 | 30.72 | 44.75 | 31.44 | 54.30 |


Cluster 0 has the highest mean PM10, PM2.5, NO2 and SO2 among these groups. Cluster 1 has the highest mean O3 and lower means for the other four variables. Cluster 2 has intermediate profiles. Cluster numbers are arbitrary, and the analysis does not establish causes of these differences.

## Visualisations

**Pollutant correlations**

![Correlation matrix](images/correlation-matrix.png)

**Elbow method and silhouette diagnostics**

![Elbow method](images/elbow-method.png)

![Silhouette analysis](images/silhouette-analysis.png)

**PCA cluster visualisation**

![K-Means clusters visualised with PCA](images/pca-clusters.png)

Additional plots are available in [`images/`](images/).

## How to run

```bash
python -m venv .venv
# macOS/Linux
source .venv/bin/activate
# Windows PowerShell: .venv\Scripts\Activate.ps1
pip install -r requirements.txt
jupyter notebook air_pollution_kmeans.ipynb
```

Place `airpoll.csv` in the same folder before running. The saved notebook outputs can be viewed on GitHub without executing the code.

## Limitations and future improvements
- **Dataset documentation:** Identify the source, licence, units, location and time span.
- **Cluster validation:** Report the actual silhouette scores and assess stability across different seeds and choices of k.
- **Interpretation:** Do not label clusters as safe or unsafe without measurement units, standards and contextual information.
- **Radar plot:** The notebook's radar chart uses `ylim(0, 40)`, which clips values above 4. Replot with a suitable scale or normalised profiles before using it in presentations.
- **Reproducibility:** The saved figures and results come from the uploaded notebook; the missing CSV prevented an independent rerun.

## Skills demonstrated
Exploratory data analysis · Data standardisation · K-Means clustering · Elbow method · Silhouette analysis · PCA · Data visualisation · Interpretation of unsupervised learning results

## Author
Nontokozo Dladla — MSc Data Science Candidate, University of the Witwatersrand
