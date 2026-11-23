# Task 17 - Customer Engagement Feature

`is_highly_engaged` and a dynamic `engagement_score` (0-100) from session time series, statistical thresholds and clustering.

## Data caveat
The dataset has no session, timestamp or customer-id columns. Modes (set `SESSION_MODE`):
- `simulated` (default): seeded synthetic weekly sessions driven by real signals (feedback received, review effort, recommendation, opinion strength) plus noise. Columns are prefixed `sim_`. This is an **engagement proxy**, not observed behaviour.
- `real`: use your own session log (user id + date) via `REAL_SESSIONS_FILE`.
- `proxy`: no time series; static signals only.

## Input
Newest available file in `data/processed/` (sentiment_features preferred).

## Outputs
| File | Content |
|---|---|
| `data/processed/womens_clothing_engagement_features.csv` | Input dataset plus engagement columns |
| `reports/task_17_engagement_cluster_profile.csv` | Profile of each engagement level |
| `reports/task_17_engagement_thresholds.csv` | Statistical cut-offs used |
| `reports/task_17_analysis_status.csv` | Run summary |

## Method
1. Weekly activity series (12 weeks) -> mean, recent mean, EWMA, trend slope, volatility, burstiness, active-week ratio, longest inactive streak.
2. Engagement index (weighted z-scores), threshold = mean + 0.5 sd with recent activity >= median.
3. K-means (k = 3..5, silhouette) -> ordered levels.
4. `engagement_score` = 60% percentile rank + 40% cluster position; `is_highly_engaged` = passes threshold AND in top clusters.

## Columns added
`engagement_index`, `engagement_stat_high`, `engagement_cluster_id`, `engagement_level`, `engagement_score`, `is_highly_engaged`, `engagement_data_mode`, `sim_*` (time-series features), `eng_feedback_received`, `eng_review_effort`
