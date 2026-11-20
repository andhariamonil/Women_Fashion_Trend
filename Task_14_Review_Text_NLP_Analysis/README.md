# Task 14 - Product Text NLP Analysis

Analyzes product title and tag text and its association with catalog ratings. The available dataset contains no customer review text; the analysis does not treat product text as reviews.

## Input
- `data/processed/womens_clothing_final.csv`

## Outputs
- `data/processed/womens_clothing_product_text_features.csv`
- `reports/task_14_product_text_analysis.csv`
- `reports/task_14_product_text_terms.csv`
- `reports/task_14_analysis_status.csv`

Extracted features include text length, word count, lexical diversity, punctuation counts, and VADER sentiment. A TF-IDF logistic regression estimates cross-validated ROC-AUC for high-rating classification.

## Run
```text
jupyter notebook Task_14_Review_Text_NLP_Analysis.ipynb
```
