
## Overview
This project solves two sequential data problems:
1. Stock price prediction using LSTM (Regression)
2. Baseline comparison using moving average

The goal is to demonstrate proper handling of time-series data and evaluate whether deep learning adds value over simple methods.

---

## Dataset
- stock_prices.csv
- Target: Next-day closing price

---

## Project Structure
week-08/
└── thursday/
├── THURSDAY_BAND4_NOTEBOOK.ipynb
├── stock_prices.csv
└── README.md

---

## How to Run
1. Open notebook in Google Colab
2. Upload dataset:

3. Run all cells

---

## Approach

### 1. Data Preparation
- Sorted data by date to maintain sequence
- Used only past data to predict future values
- Normalized values using MinMaxScaler

---

### 2. Sequence Creation
- Window size = 10 days
- Each input contains past 10 days
- Output = next-day closing price

**Why window = 10?**
- Captures short-term trends
- Avoids overfitting from long sequences

---

### 3. Train-Test Split
- Used chronological split (80% train, 20% test)

**Why NOT random split?**
- Causes data leakage
- Model sees future data during training
- Produces unrealistic high accuracy

---

### 4. Model (LSTM)
- 2 LSTM layers
- Dense output layer
- Loss: Mean Squared Error (MSE)

---

### 5. Evaluation
- Metric: RMSE (Root Mean Squared Error)

**Why RMSE?**
- Same unit as stock price
- Penalizes large errors

---

### 6. Baseline Model (Hard Step)
- Moving average of last 10 days

**Purpose:**
- Compare simple vs deep learning

---

## Results

- LSTM RMSE: (output from notebook)
- Baseline RMSE: (output from notebook)

**Insight:**
- If LSTM < Baseline → model captures patterns
- If Baseline ≤ LSTM → model overfitting / insufficient data

---

## Key Learnings
- Time-series requires sequential split
- LSTM captures temporal dependencies
- Baselines are essential for validation
- Complex models are not always better

---

## AI Usage

### Prompt Used
"Create LSTM model for stock price prediction with proper time-series handling"

### Critique
- Initial output lacked baseline comparison
- Added proper sequence creation and split
- Improved evaluation logic

---

## Requirements
- Python 3.8+
- pandas
- numpy
- matplotlib
- scikit-learn
- tensorflow

---

## Author
Hiten Mistry
