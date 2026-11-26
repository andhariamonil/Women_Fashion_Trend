# Task 25 - Linear Regression with Feature Selection and Interactions

## Target (important)
There is no `yearly amount spent` column. The target is **`log_revenue = log1p(price x units_sold)`**, an estimated product revenue snapshot (not yearly; `units_sold` is bucketed). Rename `TARGET_NAME` if you get a real spend column.

## Leakage control
`units_sold`, `rating_count` and columns built from them (engagement, `ch_*`, `lc_*`, `te_*`, shrunk-rating columns) are excluded. Price columns are allowed but make part of the fit mechanical, so a **price-only baseline** is reported; `INCLUDE_PRICE_FEATURES = False` drops them.

## Method
- Pool: numeric candidates, log1p for skewed columns, correlation filter (|r| > 0.95)
- Selection (nested inside CV): F-test, mutual information, Lasso-based, RFE, forward sequential selection, no selection; k = 5-30
- Interactions: pairwise products and squares of the 8 strongest features; FDR-corrected p-values + CV-gain screen + greedy forward addition (max 5)
- Robustness: repeated 5x3 CV, selection frequency across folds, bootstrap coefficient sign stability

## Outputs
- `data/processed/womens_clothing_regression_dataset.csv` (target, `cv_fold`, pool features, interaction candidates; read by Tasks 26-27)
- `reports/task_25_feature_selection_results.csv`, `task_25_selected_features.csv`, `task_25_interaction_terms.csv`, `task_25_model_comparison.csv`, `task_25_analysis_status.csv`

Needs `statsmodels`. Runtime about 1-3 minutes.
