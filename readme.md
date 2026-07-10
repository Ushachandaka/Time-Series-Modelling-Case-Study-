# German Electricity Demand Forecasting
## 7PAM2016 — Time Series Modelling Case Study
**MSc Data Science | University of Hertfordshire**
Student: Gopikrishna Godishala | ID: 24090533

## Overview
This project builds a complete forecasting pipeline for German weekly 
electricity demand (2015–2020) using data from Open Power System Data (OPSD).

## Models Implemented
- Benchmark models: Mean, Naive, Seasonal Naive, Drift
- SARIMA with stepwise AIC order selection
- SARIMAX with temperature covariates (HDD/CDD)
- Random Forest and Gradient Boosting
- Stacked LSTM and Bidirectional LSTM (hourly data)

## Data Sources
- Electricity load: https://data.open-power-system-data.org/time_series/
- Temperature: https://archive-api.open-meteo.com/v1/archive

## How to Run
1. Open `run_german_electricity_forecasting_gopikrishna_FINAL.ipynb` in Google Colab
2. Upload `time_series_60min_singleindex.csv` to Colab file browser
3. Runtime → Run all

## Key Results
| Model | RMSE (MW) | Skill vs Seasonal Naive |
|-------|-----------|------------------------|
| LSTM Stacked (168h) | 120.7 | +0.96 |
| BiLSTM (168h) | 1,178.2 | +0.62 |
| Random Forest | 2,695.4 | +0.12 |
| Gradient Boosting | 2,820.1 | +0.08 |
| Seasonal Naive | 3,073.5 | 0.00 |
| SARIMA(1,0,0)(1,0,0)[52] | 3,247.2 | -0.06 |

## Dependencies
```
pandas, numpy, matplotlib, statsmodels, pmdarima,
scikit-learn, tensorflow, requests
```
