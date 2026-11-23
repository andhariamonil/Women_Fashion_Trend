# Task 18 - Categorical Encoding with High-Cardinality Handling

One-hot encoding without feature explosion, using target encoding, frequency-based binning and dimensionality reduction.

## Input
Newest available file in `data/processed/` (engagement_features preferred).

## Outputs
| File | Content |
|---|---|
| `data/processed/womens_clothing_high_cardinality_encoded.csv` | Input dataset plus encoded columns (originals kept) |
| `reports/task_18_encoding_plan.csv` | Per-column strategy, cardinality, columns produced, width before/after |
| `reports/task_18_target_encoding_map.csv` | Level -> smoothed target mean, for scoring new data |
| `reports/task_18_analysis_status.csv` | Run summary incl. naive vs engineered width and CV AUC |

## Strategy
| Unique levels | Treatment |
|---|---|
| <= 10 | one-hot (`oh_*`) |
| 11-50 | bin levels under 2% to `Other`, one-hot, plus target encoding (`te_*`) |
| > 50 (e.g. Clothing ID) | out-of-fold smoothed target encoding (`te_*`), frequency encoding (`fe_*`), 5 SVD components (`svd_*`) |

Free text, constant columns and row-unique ids are excluded. Target: `Recommended IND` (or Rating >= 4).

## Notes
- Target-encoded training values are out-of-fold. For later modelling, refit the encoding inside each CV fold to avoid leakage.
- `womens_clothing_categorical_encoded.csv` from earlier work is not modified.
