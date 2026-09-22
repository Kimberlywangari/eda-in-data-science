# eda-in-data-science

## HR Attrition — EDA & Visualization (Track I, I1)

Exploratory data analysis on the IBM HR Analytics Employee Attrition dataset (Kaggle),
built as part of the AI Data Science track.

## Structure
- `data/raw/` — original, untouched dataset
- `notebooks/` — EDA notebook (data understanding → univariate → bivariate → visualization → findings)
- `reports/` — data story write-up

## Dataset
IBM HR Analytics Employee Attrition & Performance dataset — a synthetic, industry-style
HR dataset released by IBM for analytics practice (not real employee records).
1,470 rows, 35 columns (32 after removing constant columns). Source: Kaggle.

## How to run
```bash
pip install pandas numpy matplotlib seaborn jupyter
jupyter notebook notebooks/eda.ipynb
```

## Key finding
Employees who work overtime leave at ~3x the rate of those who don't (30.5% vs
10.4%) — but overtime alone doesn't explain department-level differences: Sales has
the highest attrition (20.6%) despite a similar overtime rate to other departments,
pointing to Sales-specific pressures worth investigating first.
Full findings and recommendation in `reports/data_story.md`.