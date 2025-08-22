# Titanic Survival Prediction with Random Forest

This project explores survival prediction on the Titanic dataset using a Random Forest Classifier.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ben-phillips-5227/data-analyst-portfolio/blob/main/projects/Titanic_RandomForest/notebooks/RandomForest.ipynb)

Predict passenger survival on the Titanic using a production-style **scikit-learn Pipeline**:
- **Preprocessing**: median imputation for numeric features; one-hot encoding for categoricals
- **Model**: RandomForestClassifier (seeded for reproducibility)
- **Evaluation**: Accuracy, Precision/Recall/F1, ROC-AUC; Confusion Matrix / ROC / PR plots
- **Artifacts**: Saved pipeline (`.pkl`), test predictions (`.csv`), and figures (`.png`)

## Dataset

Expected columns in `titanic.csv` (same folder as the notebook):

| Column  | Type    | Notes                              |
|---------|---------|------------------------------------|
| Age     | numeric | may contain missing values         |
| Fare    | numeric | ticket price                       |
| Gender  | string  | e.g., Male / Female                |
| Class   | string  | e.g., 1st / 2nd / 3rd              |
| Survival| string/int | “Survived”/“Died” or 0/1 target |

> The notebook maps `Survival` to 0/1 internally.

## Method

1. **Stratified split** (70/30) to preserve class balance.
2. **Pipeline**
   - `SimpleImputer(strategy="median")` for `Age`, `Fare`
   - `OneHotEncoder(drop="first", handle_unknown="ignore")` for `Gender`, `Class`
   - `RandomForestClassifier` (fixed `random_state`)
3. **Tuning** with `RandomizedSearchCV` (5-fold, scoring=ROC-AUC)
4. **Evaluation**: `classification_report`, ROC-AUC; plots for Confusion Matrix, ROC, and Precision-Recall
5. **Threshold tuning** to pick an F1-optimal cutoff
6. **Artifacts** written to `artifacts_rf/`

## Results (example run)

**Best params** (from RandomizedSearchCV):  
`n_estimators=716, max_depth=7, max_features='sqrt', min_samples_split=4, min_samples_leaf=1, class_weight=None`  
**CV ROC-AUC (mean)** ≈ **0.862**

**5-fold CV (mean ± std)**
  - Accuracy ≈ **0.784 ± 0.027**  
  - Precision ≈ **0.734 ± 0.040**  
  - Recall ≈ **0.683 ± 0.047**  
  - F1 ≈ **0.707 ± 0.036**  
  - ROC-AUC ≈ **0.843 ± 0.029**

**Held-out test** (tuned pipeline):
  - Accuracy ≈ **0.80**  
  - ROC-AUC ≈ **0.85**  
  - Average Precision (PR-AUC) ≈ **0.83**

> ROC-AUC summarizes ranking quality across **all** thresholds and is more informative than raw accuracy when classes are imbalanced.

## Artifacts

Created in `projects/Titanic_RF/artifacts_rf/`:

- `rf_pipeline.pkl` — serialized **end-to-end Pipeline** (preprocessing + model)
- `predictions_test.csv` — test set predictions with `index`, `y_true`, `y_proba`, `y_pred@0.5`
- `confusion_matrix.png`, `roc_curve.png`, `pr_curve.png` — evaluation figures
- `feature_importances.png` — top 10 features (after encoding)

### Preview (once artifacts are generated)

![Confusion Matrix](artifacts_rf/confusion_matrix.png)
![ROC Curve](artifacts_rf/roc_curve.png)
![Precision–Recall Curve](artifacts_rf/pr_curve.png)
![Feature Importances](artifacts_rf/feature_importances.png)
