# Task 15 - Dynamic Product Sales Segmentation

Segments product listings by sales volume. The available catalog has no customer age column, so this notebook does not fabricate age groups.

## Input
- `data/processed/womens_clothing_final.csv`

## Outputs
- `data/processed/womens_clothing_product_segmented.csv`
- `reports/task_15_sales_cluster_comparison.csv`
- `reports/task_15_product_segment_summary.csv`
- `reports/task_15_analysis_status.csv`

K-means finds dynamic boundaries using `log1p(units_sold)`. A rating-guided decision tree provides a second boundary comparison. The output includes selected K-means segments and tree segment labels.

## Run
```text
jupyter notebook Task_15_Dynamic_Age_Group_Segmentation.ipynb
```
