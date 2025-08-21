# Airline Delay Clustering Analysis

This project explores uses unspurvised machine learning applying K-Means clustering to U.S. airline delay data in order to identify meaningful patterns in flight delays.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ben-phillips-5227/data-analyst-portfolio/blob/main/projects/Airline_Clustering/notebooks/Clustering.ipynb)

## Project Overview
- Cleans the data and standardizes features for distance-based clustering  
- Compares k = 2-10 using *Calinski–Harabasz (CH) and Davies–Bouldin (DBI)  
- Fits K-Means with multiple initializations and a fixed random seed  
- Profiles clusters and exports assignments, centroids, and figures

## Data

- **File:** `data/AirlineDelays.csv`  
- **Rows:** 9697
- **Columns:** 18

## Methods Used
1. **Preprocessing** – select features, drop rows with NAs in those features, scale with `StandardScaler` (mean=0, std=1).  
2. **Model selection** – evaluate k=2-10 with:
   - **CH (↑)**: higher = tighter/clearer clusters  
   - **DBI (↓)**: lower = better separation  
   **Chosen k:** **4** (best balance + interpretable segments)
3. **Clustering** – `KMeans(n_clusters=4, n_init=30, random_state=42)`  
4. **Interpretation** – per-cluster means/medians/std (original units) and a PCA scatter for a 2-D visual check.

## Results
- **k=4** balances high CH and low DBI; see `artifacts/quality_metrics.png` & `artifacts/elbow.png`.  
- Example narratives (tune to your data):
  - **C0 — Long-haul punctual:** high `Distance`, low `ArrDelay/DepDelay`  
  - **C1 — Short-haul late departures:** low `Distance`, `DepDelay` >> `ArrDelay`  
  - **C2 — Moderate delays:** mid `CRSDepTime`, modest delays  
  - **C3 — Late-night arrivals:** extreme `CRSDepTime`, elevated `ArrDelay`

## Artifacts
- [artifacts/assignments.csv](./artifacts/assignments.csv) — dataset rows used + `cluster` label  
- [artifacts/cluster_profile.csv](./artifacts/cluster_profile.csv) — per-cluster mean/median/std/count (original units)  
- [artifacts/cluster_centroids_standardized.csv](./artifacts/cluster_centroids_standardized.csv) — centroids in z-scores  
- [artifacts/cluster_centroids_original_units.csv](./artifacts/cluster_centroids_original_units.csv) — centroids back-transformed  
- [artifacts/quality_metrics.png](./artifacts/quality_metrics.png) · [artifacts/elbow.png](./artifacts/elbow.png) · [artifacts/pca_scatter.png](./artifacts/pca_scatter.png)

## How to Run: Google Colab
- Click the badge at the top
- In Google Colab, click Runtime in the ribbon, then restart and run all
- I have the artifacts in their own folder, but if you would like to download them yourself, they will be downloadable after running the final cell!
