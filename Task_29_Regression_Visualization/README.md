# Task 29 - Regression Visualization

Interactive Plotly views of the Task 28 predictions (Task 26 linear baseline shown alongside when present).

## Plots
1. Actual vs predicted, colour = absolute error, ideal line, 95% CI band of the calibration line and 90% prediction-interval band
2. Same scatter by error bucket (small / medium / large / outside interval), legend-clickable
3. Tuned model vs linear baseline side by side
4. Residual histogram (train OOF vs hold-out), residual vs predicted with binned means and CIs, residuals by actual-value decile
5. Mean residual by group (category, price tier, ...) with FDR-corrected bias tests

Prediction intervals come from train out-of-fold residuals per predicted-value bin; coverage is checked on the hold-out rows.

## Outputs
- `data/processed/womens_clothing_regression_results.csv`
- `reports/task_29_actual_vs_predicted.html`, `task_29_residual_analysis.html` (open in a browser)
- `reports/task_29_bias_by_group.csv`, `task_29_interval_coverage.csv`, `task_29_calibration.csv`, `task_29_analysis_status.csv`

Run Task 28 first.
