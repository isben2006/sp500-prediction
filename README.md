# S&P 500 Price Movement Prediction Using Logistic Regression

## Overview
This project predicts whether the S&P 500 index will close higher or lower the next day using logistic regression on technical indicators derived from historical price data.

## Motivation
Predicting short-term stock movements is a challenging problem in finance. This project explores how classic technical indicators combined with a simple machine learning model can provide meaningful insights into market direction.

## Data Source
- Ticker: ^GSPC (S&P 500 Index)  
- Source: Yahoo Finance via `yfinance`  
- Period: January 1, 2020 – July 31, 2025

## Features 
| Feature Name           | Description                                      | Lookback Window (days)  |
|-----------------------|------------------------------------------------|------------------------|
| Daily Return          | Percentage price change from previous day       | 1                      |
| 5-day Moving Average  | Average close price over the past 5 days        | 5                      |
| 10-day Moving Average | Average close price over the past 10 days       | 10                     |
| Momentum (5-day)      | Difference between today’s and 5 days ago close | 5                      |
| Rolling Std Dev (10-day) | Standard deviation of close prices over 10 days | 10                     |
| Average True Range (ATR) | Measure of volatility over 14 days             | 14                     |
| Relative Strength Index (RSI) | Momentum oscillator over 14 days           | 14                     |
| Lagged Return (1-day) | Previous day’s return                            | 1                      |
| MACD                  | Moving Average Convergence Divergence indicator | 26 (slow EMA)  |

## Model Performance Summary
The logistic regression model achieves around **56% accuracy**, outperforming random guessing. It is better at predicting upward price movements (with higher recall and F1-score) but struggles to identify downward movements, indicating potential class imbalance or room for improved feature engineering.

## Usage
1. Clone the repository  
2. Install required Python packages, e.g.:  
   ```bash
   pip install yfinance pandas ta scikit-learn matplotlib seaborn
3. Open and run the Jupyter notebook `sp500-prediction.ipynb` for full analysis, model training, and detailed evaluation
