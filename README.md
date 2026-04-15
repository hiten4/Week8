# Week 08 - Monday Assignment (Time Series Forecasting & Sensor Analysis)

## Overview
This assignment focuses on time series analysis and forecasting using real-world datasets. It covers stationarity testing, decomposition, model selection, and building a predictive system for equipment failure detection.

---

## Dataset

1. Ecommerce Sales Dataset
   - File: ecommerce_sales_ts.csv
   - Contains daily sales data over ~2 years

2. Sensor Dataset
   - File: sensor_data.csv
   - Contains time-based sensor readings from warehouse equipment

---

## Tasks Completed

### Sub-step 1: Time Series Characterization

- Loaded and sorted time series data by date
- Checked stationarity using Augmented Dickey-Fuller (ADF) test
- Performed seasonal decomposition to identify:
  - Trend
  - Seasonality
  - Residuals

### Key Observations
- Series is non-stationary (high p-value in ADF test)
- Clear trend and seasonal patterns present
- Requires differencing for modeling

---

### Sub-step 2: Sensor Data Cleaning

- Identified missing values in dataset
- Removed null entries to prevent model failure
- Applied rolling mean to smooth noisy signals
- Ensured dataset is consistent for sequence modeling

---

### Sub-step 3: Time Series Modeling

- Used ARIMA model for forecasting
- Chose (p,d,q) based on:
  - Non-stationarity → differencing (d=1)
  - Simplicity as baseline model

### Train-Test Strategy
- Used time-based split (no random split)
- Last 30 days used as test set

### Evaluation Metric
- MAPE (Mean Absolute Percentage Error)

### Business Meaning
MAPE shows percentage error in predictions, helping inventory teams estimate how accurate forecasts are in real terms.

---

### Sub-step 4: Model Improvement

- Identified seasonality from decomposition
- Suggested SARIMA for capturing seasonal effects
- Compared baseline ARIMA vs improved approach

### Observation
- Seasonal models perform better when strong periodic patterns exist

---

### Sub-step 5: Sensor Failure Prediction

- Created rolling mean feature for stability
- Defined threshold:
  mean + 2 * standard deviation

- Flagged anomalies as potential failures

### Output
- Binary flag: failure_risk (True/False)

### Business Interpretation
- True → maintenance required
- False → normal operation

---

## How to Run

1. Upload datasets to Colab:
   /content/ecommerce_sales_ts.csv
   /content/sensor_data.csv

2. Open notebook:
   week08_monday_timeseries.ipynb

3. Install dependencies:
   pip install pandas numpy matplotlib statsmodels scikit-learn

4. Run all cells sequentially

---

## Output

- ADF test results (stationarity check)
- Decomposition plots (trend, seasonality)
- Forecast values for test period
- MAPE score
- Sensor failure risk predictions

---

## Project Structure

week08/
└── monday/
    ├── week08_monday_timeseries.ipynb
    ├── README.md

---

## Engineering Practices Followed

- Modular workflow (separate steps for each sub-task)
- Clear variable naming
- Time-aware train/test split (no leakage)
- Minimal hardcoding
- Basic defensive handling (missing values)

---

## Conclusion

This assignment demonstrates end-to-end time series analysis, from data understanding to forecasting and anomaly detection. It highlights the importance of proper preprocessing, correct evaluation strategies, and business-oriented interpretation of results.
