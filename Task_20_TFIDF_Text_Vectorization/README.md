# Task 20 - TF-IDF / Bag of Words with Feature Selection

## Data mapping
No review text exists, so text = product `title`. Target = above-median rating among products with >= 20 ratings (`TARGET_MODE = "sales"` switches to sales).

## Experiments (5-fold CV AUC, selection fitted inside folds)
BoW vs TF-IDF x n-grams (1,1)/(1,2)/(1,3) x stop words (none / English / English + data-driven domain words) x normalisation (none / Snowball stemming / WordNet lemmatization if available), then chi-square vs mutual information at k = 20..500.

## Outputs
- `data/processed/womens_clothing_tfidf_features.csv`
- `reports/task_20_vectorizer_experiments.csv`, `task_20_selected_features.csv`, `task_20_analysis_status.csv`

## Columns added
`tf_<term>` for the top 30 selected terms, `tf_selected_term_count`, `tf_has_any_selected_term`. Terms were chosen using the target; nest selection inside CV for further modelling.
