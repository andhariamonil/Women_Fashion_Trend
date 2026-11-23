# Task 16 - Sentiment Score Feature

Normalised `sentiment_score` from review text using VADER, a TF-IDF domain model and a fine-tuned DistilBERT.

## Input
Newest available file in `data/processed/` that contains review text (age_segmented -> review_text_features -> market_basket_features -> product_text_features -> ... -> final).

## Outputs
| File | Content |
|---|---|
| `data/processed/womens_clothing_sentiment_features.csv` | Input dataset plus sentiment columns |
| `reports/task_16_sentiment_model_comparison.csv` | AUC / Spearman per model on unseen rows, plus transformer validation metrics |
| `reports/task_16_analysis_status.csv` | Run summary, model used, any transformer error |

## Method
1. Silver labels from rating (>=4 positive, <=2 negative, 3 excluded from training).
2. VADER compound score (baseline).
3. TF-IDF + logistic regression, scored out-of-fold (leak-free).
4. DistilBERT fine-tuned (2 epochs, 8,000-review sample, 15% validation), then scores every review. Falls back automatically to model 3 if `torch`/`transformers` are missing or the download fails.
5. Ensemble `0.6 * domain + 0.4 * VADER`, robust min-max to 0-1 (`sentiment_score`) and z-score (`sentiment_score_z`). Reviews without text = neutral.

## Columns added
`sentiment_has_text`, `vader_compound`, `tfidf_sentiment_prob`, `dl_sentiment_prob`, `sentiment_dl_in_train`, `sentiment_raw`, `sentiment_score`, `sentiment_score_z`, `sentiment_label`, `sentiment_model_used`

## Caveats
- Supervised models learn from `Rating`; do not use `sentiment_score` to predict `Rating` without checking leakage (`sentiment_dl_in_train` flags rows the transformer saw).
- Fine-tuning on CPU takes roughly 15-40 minutes. Set `FINE_TUNE_TRANSFORMER = False` to skip.
