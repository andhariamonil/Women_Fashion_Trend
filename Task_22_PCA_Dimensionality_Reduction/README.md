# Task 22 - PCA for High-Cardinality Categoricals

Variance Threshold and an autoencoder before PCA, compared at a fixed component budget.

## Notes
- Your message was cut off after "minimizing computational ove..."; read as *computational overhead*.
- Reduced matrix = one-hot of every categorical column with more than 10 levels (e.g. `merchant_id`, `product_color`, `product_variation_size_id`) plus multi-hot product tags.

## Pipelines (K = 32 components)
1. PCA on the full one-hot matrix
2. Variance Threshold (several values) -> PCA
3. Variance Threshold -> autoencoder (sklearn MLP, bottleneck = K) -> PCA
Compared on held-out original-variance explained (dropped columns count as lost), fit time and downstream CV AUC of a logistic regression. The fastest pipeline within 1 percentage point of the best variance wins.

One-hot columns are nearly orthogonal, so PCA retains less variance than on dense numeric data; the notebook shows the exact variance curve.

## Outputs
- `data/processed/womens_clothing_pca_features.csv` (adds `pca_cat_1..32`)
- `reports/task_22_dimensionality_comparison.csv`, `task_22_pca_variance.csv`, `task_22_analysis_status.csv`

The components are unsupervised (no target used).
