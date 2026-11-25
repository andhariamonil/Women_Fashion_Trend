# Task 24 - Feature Importance, SHAP and RFE

## Target
`TARGET_MODE = "sales"` (above-median `units_sold`, default) or `"rating_positive"`.

## Leakage control
Columns built from the target are excluded and listed in the notebook output: sales target -> `units_sold`, rating counts, engagement, `ch_*`, `lc_*`, `te_*`, and everything built from the shrunk rating (`rs_*`, `rating_sentiment*`, `rating_confident`).

## Analysis
- Importance: decision tree, random forest, extra trees, gradient boosting (impurity), permutation importance, mean |SHAP|
- SHAP summary, bar and dependence plots
- Rank agreement: Spearman matrix, top-15 overlap, consensus rank
- RFECV (random forest, training split only, 1-SE rule) then RFE to the chosen size; hold-out AUC, fit time and model size compared with the full model, SHAP top-k and consensus top-k

## Outputs
- `data/processed/womens_clothing_feature_selected.csv` (id, target, selected features)
- `reports/task_24_feature_importance_comparison.csv`, `task_24_rfe_results.csv`, `task_24_model_efficiency.csv`, `task_24_analysis_status.csv`

Needs the `shap` package (in `requirements.txt`). Expect modest AUCs once leakage is removed.
