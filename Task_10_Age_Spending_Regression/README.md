# Task 10: Product Price vs. Units Sold

## Objective
Analyze the relationship between product price and units sold using:
- Polynomial regression degrees 1–5 with cross-validation
- Target transformations (log, square root, square, and Box-Cox)
- Product price bands and sales tiers
- Visualizations of sales by price band and origin country

## Input
`data/processed/womens_clothing_scaled.csv`

The notebook uses `price` as the feature and `units_sold` as the target. It validates that both columns exist and builds the feature and target arrays from the same complete rows. The provided dataset contains product data, not customer age or yearly customer spending.

## Workflow
1. Load the processed product dataset.
2. Select `price` and `units_sold` explicitly.
3. Compare polynomial regression degrees 1–5 with cross-validation.
4. Compare target transformations.
5. Segment products into price bands and units-sold tiers.
6. Save model metrics, profiles, plots, and logs.

## Outputs
- `reports/task_10_polynomial_regression.csv`
- `reports/task_10_price_band_profiles.csv`
- `reports/task_10_transformation_comparison.csv`
- `reports/task_10_units_sold_by_price_band.png`
- `reports/task_10_sales_tier_by_price_band.png`
- `reports/task_10_price_band_country_heatmap.png`
- `logs/task_10.log`

## Run
Execute after Tasks 1–6 are complete.
