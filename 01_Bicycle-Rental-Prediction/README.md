# Bicycle Rental Prediction — Washington D.C.

Predict the daily number of bicycle rentals based on weather conditions, temperature, and calendar features using data from the Capital Bikeshare system in Washington D.C. (2011–2012).

## Objective

Build a predictive model for daily bike rental demand to understand how environmental and seasonal factors influence ridership.

## Approach

1. **Data Preparation** — Loading and cleaning the dataset, type conversions
2. **Exploratory Data Analysis** — Visualizing rental patterns by weather, temperature, and time
3. **Correlation Analysis** — Identifying the strongest predictors of ridership
4. **Feature Engineering** — Creating derived features (e.g., rolling weekly averages)
5. **Model Development** — Training a Linear Regression model
6. **Model Refinement** — Iterating on feature selection to reduce RMSE

## Key Files

| File | Description |
|------|-------------|
| [`Bikes.ipynb`](./Bikes.ipynb) | Main analysis and modeling notebook |
| [`SOURCE.md`](./SOURCE.md) | Data source documentation, schema, and license |
| `day.csv` | Daily aggregated bike rental counts (731 records) |
| `hour.csv` | Hourly aggregated bike rental counts (17,379 records) |

## Data Source

Bike Sharing in Washington D.C. Dataset from [Kaggle](https://www.kaggle.com/datasets/marklvl/bike-sharing-dataset), licensed under [CC0: Public Domain](https://creativecommons.org/publicdomain/zero/1.0/). See [`SOURCE.md`](./SOURCE.md) for full schema and citation details.

*Adapted from coursework by the University of London on Coursera. The implementation, analysis, and insights are original work.*