# Airline Delay Clustering Analysis

This project explores uses unspurvised machine learning applying K-Means clustering to U.S. airline delay data in order to identify meaningful patterns in flight delays.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ben-phillips-5227/data-analyst-portfolio/blob/main/projects/Airline_Clustering/notebooks/Clustering.ipynb)

## Project Overview

The goal of this project is to gorup flights with meaningful clusters together based on delay behavior, distance, time-of-day patterns, and other variables. With these natural grouping, airline operations teams can target specific types of flights for performance improvements.

## Data

- **File:** `data/AirlineDelays.csv`  
- **Rows:** 9697
- **Columns:** 18
- 

## Goals

## Methods Used
1. **Preproccesing**
    - Select numeric features
    - Handle missing values, there were 0
    - Standardize features in order to center columns at 0
2. **Clustering**
    - Used K-Means (fixed random state)
    - 

## Artifacts: 
- [artifacts/assignments.csv](./artifacts/assignments.csv) — dataset rows used + `cluster` label  
- [artifacts/cluster_profile.csv](./artifacts/cluster_profile.csv) — per-cluster mean/median/std/count (original units)  
- [artifacts/cluster_centroids_standardized.csv](./artifacts/cluster_centroids_standardized.csv) — centroids in z-scores  
- [artifacts/cluster_centroids_original_units.csv](./artifacts/cluster_centroids_original_units.csv) — centroids back-transformed  
- [artifacts/quality_metrics.png](./artifacts/quality_metrics.png) · [artifacts/elbow.png](./artifacts/elbow.png) · [artifacts/pca_scatter.png](./artifacts/pca_scatter.png)

## How to Run: Google Colab
- Click the badge at the top
- In Google Colab, click Runtime in the ribbon, then restart and run all
- I have the artifacts in their own folder, but if you would like to download them yourself, they will be downloadable after running the final cell!
