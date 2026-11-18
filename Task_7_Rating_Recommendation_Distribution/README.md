# Task 7: Rating & Recommendation Distribution Analysis

## Objective
Analyze the distribution of ratings and recommendations using advanced
statistical techniques including Gaussian Mixture Modeling, anomaly
detection, and customer segmentation for deeper trend insights.

## Analysis Techniques

### Distribution Analysis
- Histogram with KDE overlay per rating value
- Recommendation rate by rating bucket
- GMM (Gaussian Mixture Model) with BIC/AIC model selection
- Component-wise density visualization

### Anomaly Detection
- Isolation Forest for multivariate anomaly detection
- Z-score and IQR flagging for univariate anomalies
- Anomaly heatmaps across department and division

### Segmentation
- KMeans clustering on rating + age + review_length features
- Cluster profile summary table
- Radar chart per cluster
- Recommendation rate per cluster

## Workflow
1. Load the processed dataset.
2. Visualize raw rating and recommendation distributions.
3. Fit Gaussian Mixture Models with BIC/AIC selection.
4. Detect anomalies using Isolation Forest and z-score methods.
5. Segment customers using KMeans clustering.
6. Profile clusters and compute recommendation rates.
7. Save analysis report and logs.

## Input
`data/processed/womens_clothing_scaled.csv`

## Output
- `reports/task_7_distribution_analysis.csv`
- `reports/task_7_gmm_summary.csv`
- `reports/task_7_cluster_profiles.csv`
- `logs/task_7.log`

## Run
Execute the notebook after completing Tasks 1–6.
