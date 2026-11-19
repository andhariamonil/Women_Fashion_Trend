# Task 11: Ratings vs. Feedback – Sentiment Analysis & Statistical Validation

## Objective
Investigate whether higher ratings lead to more positive feedback by:
- Applying rule-based and VADER-based sentiment analysis on review text
- Quantifying textual sentiment scores per review
- Performing statistical tests to validate rating–sentiment correlation
- Visualizing the relationship between ratings and feedback positivity

## Techniques

### Sentiment Analysis
- **VADER (Valence Aware Dictionary and sEntiment Reasoner)**: compound, pos, neu, neg scores
- **TextBlob polarity** as a cross-check metric
- **Rule-based keyword scoring**: positive / negative word frequency ratio
- Sentiment label assignment: Positive / Neutral / Negative

### Statistical Tests
- **Spearman correlation**: rating vs. compound sentiment score
- **Kruskal-Wallis H-test**: sentiment distribution across rating groups
- **Mann-Whitney U-test**: pairwise rating group comparisons
- **Chi-square test**: rating vs. sentiment label contingency table
- **Point-biserial correlation**: recommendation vs. sentiment score

### Visualizations
- Violin plot: sentiment score distribution per rating
- Box plot: compound score by rating group
- Heatmap: mean sentiment metrics by rating × recommendation
- Bar chart: sentiment label proportions by rating
- Scatter: sentiment score vs. rating (with regression line)
- Word frequency analysis per sentiment class

## Workflow
1. Load processed dataset.
2. Identify review text and rating columns.
3. Apply VADER and TextBlob sentiment analysis.
4. Assign sentiment labels.
5. Compute statistical tests.
6. Visualize distributions and correlations.
7. Save all reports.

## Input
`data/processed/womens_clothing_final.csv`

## Output
- `reports/task_11_sentiment_scores.csv`
- `reports/task_11_statistical_tests.csv`
- `reports/task_11_rating_sentiment_summary.csv`
- `logs/task_11.log`

## Run
Execute after Tasks 1–6 are complete.
