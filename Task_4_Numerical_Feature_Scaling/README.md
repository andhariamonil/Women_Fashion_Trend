# Task 4: Numerical Feature Scaling

## Objective
Apply and compare multiple scaling techniques to numerical features in the
Women's Clothing dataset.

## Techniques Used
- Min-Max Scaling
- StandardScaler
- RobustScaler
- Power Transformer (Yeo-Johnson)

## Workflow
1. Load the outlier-treated dataset.
2. Identify continuous numerical features.
3. Exclude target, ID, and binary columns.
4. Handle missing values using median imputation.
5. Apply all four scaling techniques.
6. Compare statistical properties and distributions.
7. Evaluate Ridge Regression using cross-validation.
8. Select the best-performing technique.
9. Save the scaled dataset and comparison reports.

## Target Column
`units_sold` is used as the default regression target for comparing scaling
techniques. It is not included among the scaled input features.

## Input
`data/processed/womens_clothing_final.csv`

## Output
- `data/processed/womens_clothing_scaled.csv`
- `reports/task_4_scaling_statistics.csv`
- `reports/task_4_scaling_comparison.csv`
- `logs/task_4.log`

## Run
Execute the notebook after completing Tasks 1, 2, and 3.

## Important Note
The selected scaler is based on Ridge Regression cross-validation and the
current dataset. Re-evaluate scaling when using a different model or target.
For final predictive modelling, fit preprocessing only on training data
through a pipeline to avoid data leakage.