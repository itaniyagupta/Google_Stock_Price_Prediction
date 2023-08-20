# Google_Stock_Price_Prediction

## This Project

In this project we are predicting google stock for next 10 days, evaluating which model (ARIMA or SARIMA) gives more accurate results.

### ETL, Model Building - Implementation
- Collecting (Extract) Google stock price data using the Yahoo Finance API. (yfinance is an API provided by Yahoo Finance to collect the latest stock price data.)
- For the sake of simplicity, I’ve limited the data to past 360 days (2023-07-20 to 2022-07-20)
- Transforming & Plotting the time series data.
- Figuring out whether our data is stationary or seasonal using **Seasonal Decomposition Method.**
- Plotting **ACF and PACF** plots to get an idea for p and q values.
- Building *ARIMA Model* & plotting the results.
- Building *SARIMA Model* & plotting the results.

### Observation

- Data is seasonal.
- A 6-month and 12-month seasonal pattern is visible.
- SARIMA gave more accurate results as compared to ARIMA, as data is Seasonal

## A BIT ABOUT TIME SERIES FORECASTING

- Analyzing and modeling time-series data to make future decisions.
- Applications : weather forecasting, sales forecasting, business forecasting, stock price forecasting

### ARIMA MODEL
- ARIMA means Autoregressive Integrated Moving Average. 
- ARIMA models have three parameters like ARIMA(p, d, q)
  - *Autoregressive Part (p)* :  It is number of lagged values that need to be added or subtracted from the values (label column).
  - *Integrated Part (d)* - It respresents number of times the data needs to differentiate to produce a stationary signal. 
     - Stationary Data : d = 0;
     - Seasonal Data : d = 1;
  - *Moving Average (q)* - It is number of lagged values for the error term added or subtracted from the values (label column).
 
### SARIMA MODEL
- SARIMA means Seasonal ARIMA.
- With ARIMA parameters, In this, we include seasonality variable as well.
- There is an additional set of autoregressive and moving average components.The additional lags are offset by the frequency of seasonality. (12 months, 6 months etc. depending on the dataset.)
- SARIMA models not only allow for differencing data by seasonal frequency, but also by non-seasonal differencing.

### SARIMAX MODEL
- SARIMA means Seasonal ARIMA.
- With SARIMA parameters, In this, we include exogenous variables as well. ( we use external data in our forecast)
- Some Real-world examples of exogenous variables are gold price, oil price, outdoor temperature, exchange rate.
- If we include external data, the model will respond much quicker to its affect than if we rely on the influence of lagging terms.
