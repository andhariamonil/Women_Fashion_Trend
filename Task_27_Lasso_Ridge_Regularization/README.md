# Task 27 - Lasso and Ridge Regression

Uses the Task 25 dataset (run Task 25 first). Target: `log_revenue` (see Task 25).

## Method
- `FEATURE_SET = "pool"` (all pool features + interaction candidates) or `"selected"`
- Alpha tuned on a 60-point log grid (5-fold x 3 repeats); best alpha and 1-SE alpha reported
- Nested CV (inner tunes alpha, outer scores) for OLS, Ridge, Lasso, Elastic Net: RMSE, MAE, R2
- Shrinkage: coefficient paths, non-zero count vs alpha, L1/L2 norms vs OLS, per-feature shrinkage, VIF vs shrinkage
- Coefficient behaviour: distributions per model, top-20 comparison, bootstrap spread, Lasso selection frequency

## Outputs
- `reports/task_27_alpha_tuning.csv`, `task_27_model_comparison.csv`, `task_27_coefficients.csv`, `task_27_shrinkage_summary.csv`, `task_27_analysis_status.csv`

Runtime about 2 minutes. Coefficients are on standardised features and a log target.
