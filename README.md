# Data Analyst Portfolio

Welcome! This portfolio showcases selected projects that demonstrate my skills in data cleaning, analysis, visualization, and reporting.

## About Me
I’m an aspiring data analyst with hands-on experience in Python, SQL, Tableau, and Excel. This portfolio contains real-world analyses I've completed.

## Projects (Quick Overview)
**Titanic Survival Prediction**  
Predict passenger survival with a clean, leakage-safe **scikit-learn Pipeline** (impute → one-hot encode → Random Forest). Emphasis on reproducibility and model evaluation (ROC-AUC, PR-AUC, confusion matrix), with exportable artifacts and a saved pipeline for scoring new rows.  
- **Highlights:** Stratified split, optional hyperparameter & threshold tuning, feature importances, artifacts
- **Folder:** `projects/Titanic_RandomForest/`
  
**Airline Delays Analysis**  
Unsupervised segmentation of flights using standardized numeric features (e.g., departure/arrival delay, taxi-in/out, NAS/system delays). Compared cluster quality and profiled clusters to label operational patterns (e.g., “On-time & Efficient,” “Ground-constrained,” “System-delay heavy”).  
- **Highlights:** preprocessing + scaling, k-selection trade-offs, PCA visualization, cluster profiles & assignments exported as artifacts
- **Folder:** `projects/Airline_Clustering/`

**Investigative Health Research** 
Merged County Health Rankings (2023) with USDA RUCC (2023) on FIPS; built composite indices (Health Disadvantage, Lifestyle Risk, Access & Support) and a simple decision tree to classify county health status. Barplots summarize index patterns by rural/urban codes; artifacts include the tree (PNG/SVG) and per-metric charts.  
- **Highlights:** run-anywhere notebook (local or raw GitHub files), clear joins, interpretable rules, focus on actionable drivers (access/support & behavior), artifact export + manifest  
- **Folder:** `projects/InvestigativeHealth_by_RUCC/`

## Resume
You can find my resume [here](./resume.pdf).

## Links
- [GitHub](https://github.com/ben-phillips-5227)
- [LinkedIn](https://www.linkedin.com/in/benphillips5227/)
