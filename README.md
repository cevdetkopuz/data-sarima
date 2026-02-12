# Champagne Sales Forecasting

This repository contains a comparative study of time-series forecasting methods applied to the Perrin Freres champagne sales dataset. The project evaluates the transition from classical statistical models to modern machine learning approaches.

## Project Objective
The goal is to predict monthly champagne sales while managing high variance and strong seasonal patterns. Performance is evaluated using **MAPE** (Mean Absolute Percentage Error).

## Methodology
1. **Statistical Analysis:** - Stationary check via Augmented Dickey-Fuller (ADF) test.
   - Seasonal differencing (12-month lag).
   - SARIMA model optimization using `auto_arima`.
2. **Machine Learning:** - Feature engineering (Lag-1 to Lag-12).
   - Rolling and Exponentially Weighted Moving Averages (MA/EWM).
   - Dynamic evaluation using a Random Forest Regressor.

## Results
The models were tested on a 24-month horizon:

| Model | MAPE (%) |
| :--- | :---: |
| **SARIMA (0,0,0)(0,1,0)[12]** | **29.42%** |
| **Random Forest (Optimized)** | **17.50%** |

**Key Finding:** The Random Forest model, enhanced with custom lag and trend features, reduced the forecast error by approximately **40%** compared to the SARIMA baseline.

## Tech Stack
- **Python:** Pandas, NumPy, Scikit-learn, Statsmodels, Pmdarima.
