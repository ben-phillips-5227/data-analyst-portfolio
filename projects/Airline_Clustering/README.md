# Airline Delay Clustering Analysis

This project explores U.S. airline delay data using KMeans clustering to identify meaningful patterns in flight delays.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ben-phillips-5227/data-analyst-portfolio/blob/main/projects/Airline_Clustering/notebooks/Clustering.ipynb)

## Files

- `data/AirlineDelays.csv`  
  Raw dataset of airline delays (airports, carriers, time of day, etc.)

- `notebooks/Clustering.ipynb`  
  KMeans clustering applied to preprocessed delay data

- `visualizations/`  
  Charts and elbow plots (optional)

## Methods Used

- Data cleaning with `pandas`
- Feature scaling with `StandardScaler`
- KMeans clustering using `scikit-learn`
- Elbow method and inertia scores to find optimal `k`
- Cluster labeling and visualization with `seaborn` and `matplotlib`

## How to Run

### If running locally:

```python
import pandas as pd
df = pd.read_csv("../data/AirlineDelays.csv")
