# Time-Series-Project
The project visualises trends in stock market data and explores various time-series analysis models such as ARIMA, SARMA, Prophet and deep learning model such as LTSM based on RMSE.

# Project Overview
Goal: Predict future closing prices of HDFC stock using historical stock market data.

Dataset: NIFTY50_all historical stock dataset.

Models Used:
Facebook Prophet
ARIMA (AutoRegressive Integrated Moving Average)
SARIMA (Seasonal ARIMA)
LSTM (Long Short-Term Memory Neural Network)

# Preprocessing Steps
Removed missing values using dropna().
Detected and removed outliers using the IQR method on Close prices.
Normalized data using MinMaxScaler for LSTM model.

# Models Implemented
1. Prophet
Captures trend and seasonality.
Automatically handles missing values and holidays.
Forecasted 90 future days.

2. ARIMA
Traditional time series model (AutoRegressive, Integrated, Moving Average).
Tuned parameters manually (order=(p,d,q)).

3. SARIMA
Extends ARIMA with seasonal components ((p,d,q)(P,D,Q,s)).
Good for capturing monthly/quarterly seasonality.

4. LSTM
Deep learning RNN architecture designed for sequences.
Used look_back=60 timesteps.
Built with TensorFlow/Keras.
Trained for 10 epochs.

# Model Evaluation (RMSE)

| Model    | RMSE (Lower is better) |
| -------- | ---------------------- |
| Prophet  | *144.05*          |
| ARIMA    | *357.68*          |
| SARIMA   | *305.83*          |
| **LSTM** | **104.32**             |


# RMSE Comparison Plot
A bar chart compares RMSE scores for all models. Each bar is annotated with the actual RMSE value.

# How to Run
1. Clone this repo:

git clone https://github.com/RekhaS02/Time-Series-Analysis-with-Stock-Market-Project.git
cd Time-Series-Analysis-with-Stock-Market-Project

2. Install dependencies:

pip install pandas numpy matplotlib scikit-learn prophet statsmodels tensorflow

3. Run the notebook (Time_series_Stock_Market.ipynb) in Jupyter or Google Colab.

# Repository Structure
📁 Time-Series-Project/
├── README.md
├── Time_series_Stock_Market.ipynb
├── NIFTY50_all.csv

# Key Observations:
LSTM outperformed all traditional statistical models with the lowest RMSE (104.32), indicating the most accurate predictions.
ARIMA performed the worst with the highest RMSE (357.68), suggesting it struggled to capture the complex patterns in the stock price data.
SARIMA showed some improvement over ARIMA by incorporating seasonality, but still had a high RMSE (305.83).
Prophet provided moderate performance with an RMSE of 144.05, better than ARIMA/SARIMA but not as strong as LSTM.

#  Summary
This project compared four time series forecasting models—Prophet, ARIMA, SARIMA, and LSTM—for predicting HDFC stock prices from the NIFTY50 dataset.
The LSTM model, a deep learning approach, achieved the best forecasting accuracy based on RMSE, thanks to its ability to learn long-term temporal dependencies in the data.
Prophet performed reasonably well and is easy to implement, making it suitable for trend/seasonality modeling.
ARIMA and SARIMA, though widely used in classical time series analysis, were less effective for this financial dataset, likely due to its high volatility and non-linearity.

# Conclusion:
LSTM is the most effective model for forecasting HDFC stock prices in this project, while Prophet provides a good balance between interpretability and accuracy.






