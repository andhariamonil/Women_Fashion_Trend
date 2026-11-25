# Task 23 - Rating -> Sentiment Categories

Dynamic thresholds, validation with sentiment analysis, and encoding-scheme comparison.

## Data mapping
`rating` is a product-level average, so the basis is the **shrunk rating** (shrunk toward the global mean by vote count, `PRIOR_STRENGTH = 20`). When `rating_*_count` columns exist, a vote-mix index is a second basis.

## Threshold schemes (recomputed from the data every run)
fixed 3/4, tertiles, outer quartiles, mean +- 0.5 sd, median +- scaled MAD, 1-D K-means, Gaussian mixture, vote-share index.

## Validation
VADER on titles by class (monotonic order, Kruskal, eta-squared), TF-IDF logistic AUC for positive vs negative titles, and vote-mix ordering. Titles are marketing copy, so expect weak text validation.

## Encodings
ordinal, one-hot, positive-vs-rest, negative-vs-rest, fold-wise target encoding, plus raw-rating and no-sentiment baselines. Predictive power = CV AUC for above-median `units_sold` (random forest, encoding fitted inside each fold, `log(rating_count)` included as a control because shrinkage couples the label to rating count).

## Outputs
- `data/processed/womens_clothing_rating_sentiment_encoded.csv`
- `reports/task_23_threshold_schemes.csv`, `task_23_encoding_comparison.csv`, `task_23_sentiment_validation.csv`, `task_23_analysis_status.csv`

## Columns added
`rating_sentiment`, `rating_sentiment_ord`, `rating_sentiment_negative/neutral/positive`, `rating_sentiment_pos_vs_rest`, `rating_sentiment_target_enc_oof`, scheme and threshold columns, `rating_confident`, `rs_*` bases.
Do not use them to predict the rating itself.
