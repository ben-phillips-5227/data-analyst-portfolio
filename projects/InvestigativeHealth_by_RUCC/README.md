#  Investigative Health Analysis by RUCC

This project explores health-related datasets with a focus on Rural-Urban Continuum Codes (RUCC) classification. The analysis investigates patterns in healthcare access, health outcomes, and other demographic indicators by urbanicity level.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ben-phillips-5227/data-analyst-portfolio/blob/main/projects/InvestigativeHealth_by_RUCC/notebooks/InvestigativeHealthRUCC.ipynb)

---

## Files

- `notebooks/InvestigativeHealthRUCC.ipynb`  
  Main Jupyter Notebook containing the analysis

- `data/` *(optional)*  
  Place any datasets used here if publicly shareable

---

## Methods Used

- Data cleaning and preprocessing with **pandas**
- Exploratory data analysis (EDA) with **matplotlib** and **seaborn**
- Grouping and aggregation by RUCC classification
- Statistical summaries and visualizations

---

## How to Run

### If running locally:
```python
import pandas as pd
df = pd.read_csv("../data/your_dataset.csv")
