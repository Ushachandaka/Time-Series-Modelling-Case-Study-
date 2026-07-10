# German Electricity Demand Forecasting
## 7PAM2016 – Time Series Modelling Case Study
**MSc Data Science | University of Hertfordshire**

**Student:** Usha Chandaka  
**Student ID:** 24075990
---

# Overview

This project develops and evaluates a complete electricity demand forecasting pipeline for Germany using historical electricity load data from **Open Power System Data (OPSD)** and historical weather data from **Open-Meteo**.

The study compares classical statistical forecasting methods, machine learning algorithms, and deep learning models to determine the most suitable approach for operational electricity demand forecasting.

The analysis includes exploratory data analysis, benchmark forecasting, SARIMA and SARIMAX models, feature-based machine learning models, and recurrent neural networks.

---

# Dataset

**Electricity Demand**

- Source: Open Power System Data (OPSD)
- Country: Germany
- Frequency: Hourly
- Study Period: January 2015 – October 2020

**Weather Data**

- Source: Open-Meteo Historical Weather API
- Location: Berlin, Germany
- Variable: Daily temperature aggregated to weekly averages

---

# Models Implemented

### Benchmark Forecasting Models

- Mean Forecast
- Naive Forecast
- Seasonal Naive Forecast
- Drift Forecast

### Statistical Models

- SARIMA (Automatic AIC model selection)
- SARIMAX (Temperature as exogenous variables)

### Machine Learning Models

- Random Forest Regressor
- Gradient Boosting Regressor

### Deep Learning Models

- Stacked LSTM
- Bidirectional LSTM (BiLSTM)

---

# Data Processing

The forecasting pipeline includes:

- Data cleaning
- Missing value checking
- Hourly to weekly aggregation
- Exploratory Data Analysis (EDA)
- Seasonal decomposition
- Stationarity testing (ADF and KPSS)
- Lag feature engineering
- Rolling statistics
- Calendar features
- Temperature feature engineering
- Feature scaling
- Model evaluation

---

# Evaluation Metrics

Forecast performance is evaluated using:

- Root Mean Squared Error (RMSE)
- Mean Absolute Error (MAE)
- Mean Absolute Percentage Error (MAPE)

The Seasonal Naive model is used as the primary benchmark for comparison.

---

# Final Model Performance

| Model | RMSE (MW) | MAE (MW) | MAPE (%) |
|--------|----------:|---------:|---------:|
| **Stacked LSTM** | **128.7** | **105.6** | **0.30** |
| **Bidirectional LSTM** | **704.3** | **561.2** | **1.34** |
| **Random Forest** | **2663.0** | **1963.0** | **3.80** |
| **Gradient Boosting** | **2680.5** | **2028.3** | **3.90** |
| **Seasonal Naive** | **3006.8** | **2318.5** | **4.41** |
| **SARIMAX** | **3223.1** | **2476.4** | **4.69** |
| **SARIMA** | **5585.0** | **4373.2** | **8.40** |

---

# Key Findings

- Strong annual seasonality dominates German electricity demand.
- Seasonal Naive provides a highly competitive benchmark.
- SARIMAX improves substantially over SARIMA after incorporating temperature variables.
- Random Forest and Gradient Boosting outperform both statistical models.
- The Stacked LSTM achieves the highest forecasting accuracy.
- Considering forecasting accuracy, interpretability, computational cost and maintainability, **Random Forest is recommended as the preferred operational forecasting model**.

---

# Repository Contents

```
German_Electricity_Demand_Forecasting_Report.docx
run_german_electricity_forecasting_gopikrishna_FINAL.ipynb
README.md
plots/
```

The **plots/** directory contains all figures used within the report, including:

- Exploratory analysis
- Seasonal decomposition
- Benchmark forecasts
- SARIMA diagnostics
- SARIMA forecast
- SARIMAX forecast
- Feature importance
- Machine learning forecasts
- LSTM training history
- LSTM forecasts
- RMSE comparison
- Overall model comparison

---

# How to Run

1. Open

```
run_german_electricity_forecasting_gopikrishna_FINAL.ipynb
```

using **Google Colab** or **Jupyter Notebook**.

2. Download the OPSD electricity dataset from

https://data.open-power-system-data.org/time_series/

3. Upload the required CSV file into the notebook environment.

4. Run all notebook cells sequentially.

The notebook automatically performs:

- Data preprocessing
- Feature engineering
- Model training
- Forecast generation
- Performance evaluation
- Figure generation

---

# Software Requirements

Python 3.11+

Required packages:

```
pandas
numpy
matplotlib
statsmodels
pmdarima
scikit-learn
tensorflow
requests
scipy
```

---

# Data Sources

Electricity Demand

https://data.open-power-system-data.org/time_series/

Historical Weather

https://archive-api.open-meteo.com/v1/archive

---

# References

- Open Power System Data (2020). Time Series Data Package.
- Open-Meteo Historical Weather API.
- Hyndman, R.J. & Athanasopoulos, G. (2021). *Forecasting: Principles and Practice*.
- Breiman, L. (2001). *Random Forests*.
- Hochreiter, S. & Schmidhuber, J. (1997). *Long Short-Term Memory*.

---

**Module:** 7PAM2016 – Time Series Modelling Case Study

**University of Hertfordshire**

**MSc Data Science**
