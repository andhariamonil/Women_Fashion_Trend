# Task 1 — Data Cleaning

## Objective
Remove exact duplicate rows and identify redundant columns without discarding useful product or merchant information.

## Input
Place the original dataset at `data/raw/womens_clothing.csv`.

## Run
Open `notebooks/Task_1_Data_Cleaning.ipynb` and run all cells from top to bottom.

## Output
- `data/interim/womens_clothing_cleaned.csv`
- `logs/task1_duplicate_log.json`
- `logs/task1_column_log.json`
- `logs/task1_summary.json`

## Cleaning policy
Only entirely empty and constant columns are automatically removed (unless protected). Product IDs, merchant IDs, URLs, image fields, and descriptive fields are retained. Product-ID-based deduplication is disabled by default because different variations or crawls can be legitimate separate records.
