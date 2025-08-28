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

## Aggregate Variables
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

## Summary of Findings (from the 4 artifacts)

**1) Decision tree — Urbanization & Environment–Lifestyle predictors**  
_File:_ `artifacts/decision_tree_urbanization_env.png` (and `.svg`)  
The tree classifies counties as **Less Healthy vs. Healthier** using a small set of interpretable rules. Early splits are driven by **access & environment** (e.g., *PCP_Rate*, *ExerciseAccess*, *FoodEnv*), with **lifestyle factors** (*Smoking*, *Drinking*) refining the decision. **Urban_Code** (metro/suburban/rural) contributes but is **not the sole driver**—counties with **limited access/support** and **riskier lifestyles** are most likely to be classified “Less Healthy,” regardless of urbanicity.  
**Takeaway:** Structural access (providers, exercise facilities, food environment) + lifestyle risk together explain health disadvantage more than place alone.

**2) Barplot — Health Disadvantage Index (HDI) by RUCC**  
_File:_ `artifacts/bar_hdi_by_rucc.png`  
HDI tends to **worsen as counties become more rural** (higher RUCC codes). Error bars indicate **greater variability** among rural codes, suggesting pockets of both resilience and high disadvantage.  
**Takeaway:** On average, rural counties carry a higher health burden, but outcomes are heterogeneous—targeted, local strategies are warranted.

**3) Barplot — Lifestyle Risk Index by RUCC**  
_File:_ `artifacts/bar_lifestyle_risk_by_rucc.png`  
**Lifestyle risk (e.g., obesity/inactivity proxies)** is generally **higher outside metro areas**. This aligns with the decision tree’s use of lifestyle variables to separate “Less Healthy” counties.  
**Takeaway:** Behavior-linked risks are elevated in non-metro contexts, reinforcing the need for prevention and community programs tailored to rural settings.

**4) Barplot — Access & Support Index by RUCC**  
_File:_ `artifacts/bar_access_support_by_rucc.png`  
**Access & support** (provider availability, exercise facility access, food environment) is **lowest in rural codes** and improves toward metro codes.  
**Takeaway:** **Access constraints** are a consistent differentiator—closing gaps in providers and healthy-environment supports is likely to yield the biggest improvements.


## Overall Interpretation
- Consistent rural disadvantage appears across HDI, lifestyle risk, and access/support, but with notable within-group variation, especially among rural counties.  
- The decision tree emphasizes changeable factors (access/support + behavior) more than place alone; i.e., where a county is matters, but what resources and behaviors it has matters more for classification.  
- Policy & program implication: Pair access investments (providers, facilities, food environment) with behavioral interventions (inactivity/smoking/obesity prevention). Target rural counties first, but use county-level data to prioritize specific communities given the wide spread.

## Caveats
- The indices are composite summaries; individual measures may move in different directions locally.  
- Findings are cross-sectional; causal claims require longitudinal or quasi-experimental designs.  
- RUCC captures broad urbanicity; adding geography (state/region) could explain part of the variability.

## Next Steps
- Map the indices to visualize spatial clusters and identify outliers (rural counties performing well).  
- Segment by state/region to separate rurality effects from regional policy/context.  

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
