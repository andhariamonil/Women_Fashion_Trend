# Task 19 - Interaction Features from Two Activity Channels

Transition ratio, engagement index, non-linearity detection, polynomial features and optimisation.

## Data mapping
There are no `time on app` / `time on website` columns. `CHANNEL_A = rating_count` (feedback activity) and `CHANNEL_B = units_sold` (purchase activity) stand in; change the two names to remap. Target = `rating` for products with >= 20 ratings. Your request was cut off after "optimizing it fo"; predictive performance was assumed.

## Method
Interaction metrics (ratio, share, log ratio, balance, geometric engagement, index) -> non-linearity tests (Pearson vs Spearman, mutual information, linear vs quadratic/cubic CV R2, decile plots) -> grid over base set, degree 1-3, interaction-only, RidgeCV -> Lasso-kept terms saved.

## Outputs
- `data/processed/womens_clothing_channel_interaction_features.csv`
- `reports/task_19_interaction_feature_comparison.csv`, `task_19_nonlinearity_tests.csv`, `task_19_analysis_status.csv`

## Columns added
`ch_*` interaction metrics and `ch_poly_*` selected polynomial terms. R2 is expected to be low; judge relative gain over the linear baseline.
