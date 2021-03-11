# Yen/USD Time-Series and Linear Regression Forecasting

Joshua Bond

## Overview

Time series forecasting and linear regression modeling is used to determine if predictable behavior exists in Dollar-Yen exchange rate futures data.

## Time-Series Forecasting

For the time-series analysis and modeling, the Settle price was decomposed using a Hodrick-Prescott Filter to see trend and noise. Then the following 5-day forecasts were performed:

1. ARMA model to forecast returns
2. ARIMA model to forecast settle price
3. GARCH to forecast volatility

The results for the ARMA and ARIMA models both eluded to the models being a poor fit based on insignificant p-values. The GARCH model did have significant p-values and an Adj. R-Squared value of 0. 

Based on the results, I would not feel confident using these models for trading because the ARMA and ARIMA models were a poor fit, and therefore accurate predicitons of price movements would likely not be possible. In my opinion, the only conclusion to be gained from these models is that volatility in the Yen is likely to increase in the near-term. 

## Linear Regression Forecasting 

In the linear regression component of the analysis, data was split into a training and test set. The training set was created using the first 4 years of the data (2014-2017), and the test set was created with the data from 2018-2019. Afterwards, a linear regression model was created and fit to the training data. Predicitons were then made using the testing data to evaluate the model since this set contains data that the model has never seen before.

The results were an in-sample Root Mean Squared Error (RMSE) of 0.5962037920929946, and an out-of-sample RMSE of 0.41545437184712763. This implies that the model performed better on the out-of-sample data compared to the in-sample data. Typically, the RMSE is lower for the in-sample data because this is what the model is trained on. However, this was not the case here.
