# Task 30 - Logistic Regression: Will a Product Be Recommended?

## Target
There is no `recommended` column. A product is **recommended** when its average `rating` is in the top 30% (`RECOMMEND_QUANTILE = 0.70`) of products with at least 20 ratings; the cut-off is computed from the data (override with `FIXED_THRESHOLD`).

## Leakage control
Popularity (`units_sold`, `rating_count`, vote counts) and anything built from ratings or trained on them (`rs_*`, `rating_sentiment*`, `sentiment_*`, `tf_*`, engagement, `te_*`) are excluded; the model uses engineered product attributes only.

## Method
- Feature engineering: price/discount ratios, price relative to category, shipping ratio, merchant quality and scale, title wording, tag structure, category/colour/size flags, selected interactions
- Balancing inside CV: none, class_weight, SMOTE, undersampling, SMOTE + undersampling
- Regularization: L1, L2, Elastic Net, C tuned on PR-AUC
- Interpretability-first selection: among configurations within 1 SE of the best PR-AUC, fewest non-zero coefficients
- Hold-out metrics, threshold tuning on train OOF, calibration, odds ratios with bootstrap CIs, random-forest reference

## Outputs
- `data/processed/womens_clothing_recommendation_features.csv`
- `reports/task_30_balancing_comparison.csv`, `task_30_model_metrics.csv`, `task_30_logistic_coefficients.csv`, `task_30_threshold_analysis.csv`, `task_30_analysis_status.csv`

Needs `imbalanced-learn`.
