# UK Road Traffic Accident Analysis

A data-mining and forecasting project analysing reported road traffic accidents in Great Britain using Python, SQLite, statistical testing, association-rule mining, spatial clustering, and time-series modelling.

## Project Overview

This project investigates when, where, and under what conditions road traffic accidents occurred. The analysis focuses mainly on 2018 accident records, while selected forecasting tasks use 2017–2018 data for training and 2019 data for evaluation.

The notebook combines accident, vehicle, casualty, and geographic information to explore temporal patterns, vulnerable road users, environmental conditions, spatial hotspots, and short-term accident forecasts.

## Objectives

- Analyse accident frequency by hour and day of the week.
- Compare accident patterns across motorcycle categories.
- Examine pedestrian-casualty patterns.
- Identify recurring accident-condition combinations using Apriori association rules.
- Detect West Yorkshire accident hotspots using K-Means and DBSCAN.
- Forecast weekly accident totals for high-volume police-force areas.
- Forecast short-term accident counts for high-incident West Yorkshire LSOAs.

## Dataset

The project uses reported Great Britain road-safety data stored in a SQLite database.

Main tables:

- `accident`
- `vehicle`
- `casualty`
- `lsoa`

The analysis includes:

- 122,635 accident records from 2018
- 17,478 motorcycle vehicle records
- 22,432 pedestrian casualties
- 4,132 West Yorkshire accident records with valid coordinates

## Analysis Performed

### Temporal Analysis

Accident counts were analysed by hour and weekday. Chi-square goodness-of-fit tests were used to determine whether the observed distributions differed from uniform patterns.

### Motorcycle Analysis

Motorcycles were grouped into:

- 125cc and under
- Over 125cc and up to 500cc
- Over 500cc

Hourly and weekday patterns were compared across the three categories.

### Pedestrian Casualty Analysis

Pedestrian casualties were linked with accident times and dates to identify periods of elevated risk.

### Association-Rule Mining

Apriori association rules were generated using variables such as:

- Accident severity
- Weather
- Road-surface condition
- Light condition
- Speed limit
- Urban or rural area

### Spatial Clustering

K-Means and DBSCAN were applied to West Yorkshire accident coordinates to identify broad spatial zones and dense local hotspots.

### Time-Series Forecasting

Exponential Smoothing was used to forecast:

- Weekly accident counts for selected police-force areas
- Daily accident counts for high-incident West Yorkshire LSOAs

## Key Findings

- Accident frequency peaked around 17:00.
- Friday recorded the highest total number of accidents.
- Pedestrian casualties were concentrated between 15:00 and 17:00.
- Motorcycles of 125cc and under formed the largest motorcycle group.
- West Yorkshire accidents showed clear spatial clustering.
- Forecast accuracy varied substantially between police-force areas.
- The short-term LSOA forecast achieved an MAE of approximately 0.92 and an RMSE of approximately 1.28.

## Technologies Used

- Python
- pandas
- NumPy
- SQLite
- Matplotlib
- SciPy
- scikit-learn
- mlxtend
- statsmodels
- Jupyter Notebook

## Limitations

- The dataset contains reported injury accidents rather than every road incident.
- Accident counts are not adjusted for exposure such as traffic volume.
- Association rules and clustering identify patterns but do not establish causation.
- The forecasting models are intentionally simple baselines.
- Spatial hotspots require local contextual and engineering investigation.
