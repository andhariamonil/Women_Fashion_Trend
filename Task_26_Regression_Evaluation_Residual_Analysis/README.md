# Task 26 - Regression Evaluation and Residual Analysis

Evaluates the Task 25 final model (run Task 25 first).

## Evaluation
5-fold and 10-fold CV, each repeated 5 times: RMSE, MAE, R2 on the log scale and back-transformed to revenue (Duan smearing); train vs test gap.

## Residual analysis
OOF residuals: residual vs fitted, Q-Q, histogram, scale-location, residual vs top features, leverage and Cook's distance.

## Heteroscedasticity
Breusch-Pagan, White, Goldfeld-Quandt, Spearman |resid| vs fitted, Levene across fitted deciles, RMSE by decile, plus Shapiro-Wilk and Jarque-Bera. Remedies: HC3 robust standard errors and WLS.

## Outputs
- `data/processed/womens_clothing_regression_predictions.csv` (OOF predictions, residuals, leverage, Cook's D)
- `reports/task_26_cv_metrics.csv`, `task_26_residual_diagnostics.csv`, `task_26_error_by_decile.csv`, `task_26_coefficients_ols_hc3.csv`, `task_26_analysis_status.csv`
