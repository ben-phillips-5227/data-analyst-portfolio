#  Investigative Health Analysis by RUCC

This project explores health-related datasets with a focus on Rural-Urban Continuum Codes (RUCC) classification. The analysis investigates patterns in healthcare access, health outcomes, and other demographic indicators by urbanicity level. The goal of this project wasn't to confirm or deny a hypothesis, but to gain insight on the distribution of health issues in the United States.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ben-phillips-5227/data-analyst-portfolio/blob/main/projects/InvestigativeHealth_by_RUCC/notebooks/InvestigativeHealthRUCC.ipynb)

## Data sources
- **County Health Rankings (2023)**  
  File in repo: `2023_County_Health_Rankings_Adj.xlsx`  
  Sheets used:
  - `Ranked Measure Data` *(core metrics like obesity, inactivity, mortality)*  
  - `Additional Measure Data` *(e.g., **% Adults with Diabetes**)*

- **USDA Rural–Urban Continuum Codes (2023)**  
  File in repo: `Ruralurbancontinuumcodes2023.xlsx`  
  Field used: `RUCC_2023` (categorical code 1–9)

## Methods Used
- Data sources were merged on the FIPS (Federal Information Processing Standards) codes
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

## Results
Created three aggregate variables for analysis:

      - Health Disadvantage Index (HDI):
        - % Adults with Obesity
        - % Fair or Poor Health
        - % Adults with Diabetes
        - Log of Years of Potential Life Lost Rate
      - Lifestyle Risk Index (LRI):
        - % Adults with Obesity
        - % Physically Inactive
        - % Adults Reporting Currently Smoking
        - % Excessive Drinking
      - Access Support Index (ASI): 
        - Primary Care Physician Rate
        - % With Access to Exercise Opportunities
        - Food Environment Index
        - Mental Health Provider Rate

   


## Artifacts
- **[decision_tree_urbanization_env.png](./artifacts/decision_tree_urbanization_env.png)**  
  Final decision tree using urbanization and environment/lifestyle predictors. Shows the splits/thresholds the model used to classify counties as “Less Healthy” vs “Healthier.”
- **[bar_hdi_by_rucc.png](./artifacts/bar_hdi_by_rucc.png)**  
  Mean **Health Disadvantage Index (HDI)** by RUCC code with SD error bars.
- **[bar_lifestyle_risk_by_rucc.png](./artifacts/bar_lifestyle_risk_by_rucc.png)**  
  Mean **Lifestyle Risk Index** by RUCC code with SD error bars.
- **[bar_access_support_by_rucc.png](./artifacts/bar_access_support_by_rucc.png)**  
  Mean **Access & Support Index** by RUCC code with SD error bars.

## License & attribution
- County Health Rankings © University of Wisconsin Population Health Institute.
- RUCC 2023 codes © USDA Economic Research Service.
- This notebook is for analysis/education; verify licensing before redistribution of raw files.

## How to Run: Google Colab
- Click the badge at the top
- In Google Colab, click Runtime in the ribbon, then restart and run all
