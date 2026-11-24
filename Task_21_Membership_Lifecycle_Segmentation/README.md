# Task 21 - Membership Duration and Lifecycle Stages

## Data mapping and limitation
The data has no customers, join dates or repeated snapshots, so true membership duration cannot be computed.
- `DURATION_MODE = "proxy"` (default): merchant tenure proxy from `merchant_rating_count`.
- `DURATION_MODE = "date"`: set `DATE_COL` to a real start-date column; duration = today - date, recomputed on every run.
Engagement trend is a cross-sectional momentum proxy (engagement percentile minus tenure percentile).

## Method
Duration -> log1p -> min-max (`lc_tenure_log`, `lc_tenure_norm`) -> K-means on tenure, engagement and momentum -> stages New / Growing / Established / Mature / Declining.

## Outputs
- `data/processed/womens_clothing_lifecycle_features.csv`
- `reports/task_21_lifecycle_stage_profile.csv`, `task_21_tenure_summary.csv`, `task_21_analysis_status.csv`

## Columns added
`lc_tenure_days`, `lc_tenure_log`, `lc_tenure_norm`, `lc_tenure_pct`, `lc_engagement_pct`, `lc_momentum`, `lc_trend`, `lifecycle_stage`, `lifecycle_stage_id`, `lc_tenure_mode`

In proxy mode report results as seller maturity, not membership length.
