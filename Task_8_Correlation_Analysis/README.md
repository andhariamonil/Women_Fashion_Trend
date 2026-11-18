# Task 8: Multi-Metric Correlation Analysis

## Objective
Compute correlation between numerical variables using multiple metrics
(Pearson, Spearman, Kendall), dynamically filter significant correlations,
and enhance heatmap visualizations with hierarchical clustering.

## Analysis Techniques

### Correlation Metrics
- **Pearson**: Linear correlation (parametric)
- **Spearman**: Rank-based correlation (non-parametric, monotonic)
- **Kendall**: Concordance-based correlation (robust to ties & outliers)

### Filtering
- Dynamic significance threshold (default p-value < 0.05)
- Minimum absolute correlation threshold (default |r| ≥ 0.1)
- Side-by-side comparison of all three metrics

### Visualization
- Annotated heatmaps per metric
- Hierarchical clustering dendrogram on heatmap (clustermap)
- Significance-masked heatmap (non-significant pairs masked)
- Pairplot for top correlated feature pairs
- Bar chart of top-N strongest correlations

## Workflow
1. Load the processed dataset.
2. Select all numerical columns dynamically.
3. Compute Pearson, Spearman, and Kendall correlation matrices.
4. Apply significance filtering with p-value testing.
5. Generate standard annotated heatmaps.
6. Generate hierarchically clustered heatmaps (clustermap).
7. Generate pairplot for top correlated pairs.
8. Save correlation matrices and filtered results.

## Input
`data/processed/womens_clothing_scaled.csv`

## Output
- `reports/task_8_pearson_correlation.csv`
- `reports/task_8_spearman_correlation.csv`
- `reports/task_8_kendall_correlation.csv`
- `reports/task_8_significant_pairs.csv`
- `logs/task_8.log`

## Run
Execute the notebook after completing Tasks 1–6.
