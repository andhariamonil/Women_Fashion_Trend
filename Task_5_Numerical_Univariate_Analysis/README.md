# Task 5: Numerical Univariate Analysis

## Objective
Perform univariate analysis on numerical features to understand their
distributions, detect skewness, and identify possible transformations.

## Visualizations
- Histograms
- Boxplots
- KDE plots
- Skewness comparison
- Kurtosis comparison

## Statistical Measures
- Count
- Mean
- Median
- Standard deviation
- Minimum and maximum
- Skewness
- Kurtosis

## Workflow
1. Load the outlier-treated dataset.
2. Identify numerical columns dynamically.
3. Calculate descriptive statistics.
4. Interpret skewness and kurtosis.
5. Generate custom histogram, boxplot, and KDE visualizations.
6. Identify highly skewed features.
7. Save the analysis report.

## Skewness Interpretation
- Near zero: approximately symmetric distribution.
- Positive: longer right tail.
- Negative: longer left tail.

## Input
`data/processed/womens_clothing_final.csv`

## Output
- `reports/task_5_numerical_analysis.csv`
- `logs/task_5.log`

## Run
Execute the notebook after completing Tasks 1, 2, and 3.