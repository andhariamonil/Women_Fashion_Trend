# Task 6: Categorical Univariate Analysis

## Objective
Analyze categorical features using frequency distributions, visualizations,
entropy-based importance measures, and dynamic categorical encoding.

## Analysis Techniques
- Frequency distributions
- Percentage distributions
- Bar charts
- Pie charts
- Stacked bar charts
- Shannon entropy
- Normalized entropy

## Encoding Techniques
- One-Hot Encoding for low-cardinality categories.
- Frequency Encoding for high-cardinality categories.

## Dynamic Encoding
The default category threshold is 10:
- 10 or fewer unique categories: One-Hot Encoding.
- More than 10 unique categories: Frequency Encoding.

## Workflow
1. Load the outlier-treated dataset.
2. Identify categorical columns dynamically.
3. Exclude IDs, URLs, and free-text columns.
4. Calculate category frequencies and percentages.
5. Generate bar charts and pie charts.
6. Generate stacked bar charts using a suitable grouping column.
7. Calculate entropy and normalized entropy.
8. Apply dynamic categorical encoding.
9. Save encoded data and analysis reports.

## Entropy
Shannon entropy measures the diversity or uncertainty of a categorical
feature. Higher entropy indicates a more diverse category distribution.

Normalized entropy ranges from 0 to 1 and helps compare features with
different numbers of unique categories.

## Input
`data/processed/womens_clothing_final.csv`

## Output
- `data/processed/womens_clothing_categorical_encoded.csv`
- `reports/task_6_categorical_analysis.csv`
- `reports/task_6_encoding_summary.csv`
- `logs/task_6.log`

## Run
Execute the notebook after completing Tasks 1, 2, and 3.