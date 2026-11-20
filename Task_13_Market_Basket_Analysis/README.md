# Task 13 - Product Tag Co-occurrence Analysis

Analyzes product listing tags in the available catalog. Each listing is one set of tags; there are no order or customer identifiers, so this is not transaction-level market basket analysis.

## Input
- `data/processed/womens_clothing_final.csv`

## Outputs
- `data/processed/womens_clothing_product_tag_features.csv`
- `reports/task_13_product_tag_rules.csv`
- `reports/task_13_product_tag_frequency.csv`
- `reports/task_13_analysis_status.csv`

The notebook uses up to 40 frequent tags for Apriori association rules and adds tag-count and association features to each product.

## Run
```text
jupyter notebook Task_13_Market_Basket_Analysis.ipynb
```
