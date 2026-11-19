# Task 12: App vs. Website Time – Behavior Clustering & Conversion Prediction

## Objective
Explore how time on app vs. time on website influences purchases by:
- Clustering user behavior patterns with KMeans and DBSCAN
- Detecting multicollinearity using VIF and correlation analysis
- Building predictive models (Linear Regression, Random Forest, XGBoost proxy)
  to determine which time factor has a stronger impact on conversions

## Techniques

### Clustering
- **KMeans** with Silhouette + Elbow selection
- **DBSCAN** for density-based noise-robust segmentation
- Cluster profiles: mean app time, website time, and spending per segment
- 2D scatter visualization (app time vs. website time, colored by cluster)

### Multicollinearity Detection
- **Pearson / Spearman** correlation matrix for all time-related features
- **Variance Inflation Factor (VIF)** computation per predictor
- Condition number of the feature matrix
- VIF bar chart with threshold line

### Predictive Models
- **Linear Regression** baseline with feature coefficients
- **Ridge / Lasso Regression** to handle collinearity
- **Random Forest Regressor** with feature importance ranking
- **Permutation importance** for unbiased feature ranking
- SHAP-style feature impact summary (manual approximation)

### Visualizations
- Scatter plot: App Time vs. Website Time (colored by spending tier)
- Cluster scatter plot
- VIF bar chart
- Feature importance comparison chart
- Partial dependence plots (manual) for top features
- Residual plots per model

## Workflow
1. Load processed dataset.
2. Identify app/website time and spending columns dynamically.
3. Run clustering (KMeans + DBSCAN).
4. Compute VIF and correlation.
5. Train and evaluate regression models.
6. Rank feature importance.
7. Visualize all results.
8. Save reports.

## Input
`data/processed/womens_clothing_scaled.csv`

## Output
- `reports/task_12_cluster_profiles.csv`
- `reports/task_12_vif_analysis.csv`
- `reports/task_12_model_comparison.csv`
- `reports/task_12_feature_importance.csv`
- `logs/task_12.log`

## Run
Execute after Tasks 1–6 are complete.
