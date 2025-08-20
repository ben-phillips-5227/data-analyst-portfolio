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

## How to Run

### If running locally:

```python
import pandas as pd
df = pd.read_csv("../data/AirlineDelays.csv")
