# Task 28 - Hyperparameter Tuning (Grid, Random, Bayesian)

Target: `log_revenue = log1p(price x units_sold)` (Task 25; there is no yearly-spend column). Run Task 25 first.

## Design
1. **Search comparison** on HistGradientBoosting: GridSearchCV (16 combinations), RandomizedSearchCV (`N_ITER` = 30 draws), Bayesian optimization with Optuna TPE (30 trials) - best CV RMSE, hold-out RMSE, evaluations, time, convergence curves, hyperparameter importance
2. **Model families:** Elastic Net (grid), Random Forest (randomized), HistGradientBoosting (best search), vs untuned defaults
3. **Generalization:** untouched 20% hold-out, nested CV (inner search inside each outer fold), learning curve, validation curve, CV-vs-hold-out gap

## Outputs
- `data/processed/womens_clothing_tuned_regression_predictions.csv` (train rows = out-of-fold, test rows = hold-out; all out-of-sample; used by Task 29)
- `reports/task_28_search_comparison.csv`, `task_28_model_comparison.csv`, `task_28_best_params.csv`, `task_28_search_history.csv`, `task_28_generalization.csv`, `task_28_analysis_status.csv`

Needs `optuna`. Runtime roughly 5-10 minutes with the default budget; lower `N_ITER` for a quick run.
