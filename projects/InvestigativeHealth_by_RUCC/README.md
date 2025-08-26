#  Investigative Health Analysis by RUCC

This project explores health-related datasets with a focus on Rural-Urban Continuum Codes (RUCC) classification. The analysis investigates patterns in healthcare access, health outcomes, and other demographic indicators by urbanicity level.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ben-phillips-5227/data-analyst-portfolio/blob/main/projects/InvestigativeHealth_by_RUCC/notebooks/InvestigativeHealthRUCC.ipynb)

## Data sources
- **County Health Rankings (2023)**  
  File in repo: `2023_County_Health_Rankings_Adj.xlsx`  
  Sheets used:
  - `Ranked Measure Data` *(core metrics like obesity, inactivity, mortality)*  
  - `Additional Measure Data` *(e.g., **% Adults with Diabetes**)*

- **USDA Rural–Urban Continuum Codes (2023)**  
  File in repo: `Ruralurbancontinuumcodes2023.xlsx`  
  Field used: `RUCC_2023` (categorical code 1–9),
  1 is the most urban, 9 is the most rural

## Methods Used
- Data cleaning and preprocessing with **pandas**
- Exploratory data analysis (EDA) with **matplotlib** and **seaborn**
- Grouping and aggregation by RUCC classification
- Statistical summaries and visualizations

## Key Fields

| Column                     | Source Sheet            | Meaning                                                 |
| -------------------------- | ----------------------- | ------------------------------------------------------- |
| `FIPS`                     | All                     | County FIPS code (join key)                             |
| `RUCC_2023`                | RUCC file               | Rural–Urban Continuum Code (1 metro … 9 rural)          |
| `% Adults with Diabetes`   | Additional Measure Data | Adult diabetes prevalence (percent)                     |
| `% Adults with Obesity`    | Ranked Measure Data     | Adult obesity prevalence (percent)                      |
| `% Physically Inactive`    | Ranked Measure Data     | Adults with no leisure-time physical activity (percent) |
| `Premature death` / `YPLL` | Ranked Measure Data     | Years of Potential Life Lost rate (if included)         |


## How to Run

### If running locally:
```python
import pandas as pd
df = pd.read_csv("../data/your_dataset.csv")
