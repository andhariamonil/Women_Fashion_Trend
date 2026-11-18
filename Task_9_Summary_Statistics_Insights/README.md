# Task 9: Summary Statistics & Automated Insights

## Objective
Develop a custom report generator that calculates comprehensive statistics
(mean, median, variance, skewness, kurtosis) and interprets trends using
natural language processing techniques to produce human-readable summaries.

## Analysis Techniques

### Statistical Computation
- Central tendency: mean, median, mode
- Dispersion: variance, std, IQR, range, CV (coefficient of variation)
- Shape: skewness, kurtosis
- Percentiles: P5, P25, P50, P75, P95
- Missing value and unique value counts

### NLP-Powered Interpretation
- Rule-based template engine for natural language summaries
- Skewness interpreter (highly left/right skewed, symmetric)
- Kurtosis interpreter (leptokurtic, platykurtic, mesokurtic)
- Outlier presence narration using IQR fences
- Trend narrator for categorical frequency shifts
- Automated HTML report generation

### Visualizations
- Summary dashboard (multi-panel figure per feature)
- Distribution shape comparison grid
- Box-violin hybrid plots
- Statistical summary table rendered as heatmap

## Workflow
1. Load the processed dataset.
2. Compute full descriptive statistics for all columns.
3. Run the NLP interpretation engine on each column.
4. Build structured JSON and CSV report.
5. Render an auto-generated HTML report with embedded insights.
6. Save all outputs.

## Input
`data/processed/womens_clothing_scaled.csv`

## Output
- `reports/task_9_summary_statistics.csv`
- `reports/task_9_insights_report.json`
- `reports/task_9_automated_report.html`
- `logs/task_9.log`

## Run
Execute the notebook after completing Tasks 1–6.
