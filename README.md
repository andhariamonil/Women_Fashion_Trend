# Women's Clothing — Trends and Analysis in the Fashion Industry

A continuous three-stage preprocessing project. Each task has its own folder containing its Jupyter notebook and README.

## Folder structure

```text
Womens_Clothing_ML_Project/
├── Task_1_Data_Cleaning/
│   ├── Task_1_Data_Cleaning.ipynb
│   └── README.md
├── Task_2_Standardization/
│   ├── Task_2_Standardization.ipynb
│   └── README.md
├── Task_3_Outlier_Treatment/
│   ├── Task_3_Outlier_Treatment.ipynb
│   └── README.md
├── data/
│   ├── raw/
│   ├── interim/
│   └── processed/
├── logs/
├── reports/
├── requirements.txt
└── README.md
```

## Setup

```bash
python -m venv .venv
```

Activate the environment:

**Windows**
```bash
.venv\\Scripts\\activate
```

**Ubuntu/Linux/macOS**
```bash
source .venv/bin/activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

## Add the dataset

Place your original CSV at:

`data/raw/womens_clothing.csv`

## Run in order

1. Open and run `Task_1_Data_Cleaning/Task_1_Data_Cleaning.ipynb`.
2. Open and run `Task_2_Standardization/Task_2_Standardization.ipynb`.
3. Open and run `Task_3_Outlier_Treatment/Task_3_Outlier_Treatment.ipynb`.

Run each notebook from the project root (the directory containing `requirements.txt`) so the relative paths resolve correctly. In VS Code, open the entire project root as the workspace, then open each notebook.

## Pipeline

- Task 1 reads the raw CSV and writes `data/interim/womens_clothing_cleaned.csv`.
- Task 2 reads the Task 1 output and writes `data/interim/womens_clothing_standardized.csv`.
- Task 3 reads the Task 2 output and writes `data/processed/womens_clothing_final.csv`.

Each task writes its own audit logs or reports into the shared `logs/` and `reports/` folders.
