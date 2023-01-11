
# Predicting STI market by combining LSTM and classification machine learning

This repository is used to predict Strait Times Index(STI) closing price using ARIMA and LSTM. 
Predictions are then converted to classification labels and combined with classification 
machine learning model's prediction.


## Libraries

The following libraries are used to run the project

`numpy`
`pandas`
`yfinance`
`sklearn`
`statsmodels`
`keras`
`tensorflow`


## Introduction

Workbooks are serparated into three files:
- Optimizing ARIMA and LSTM to predict LSTM 
- Optimizing LSTM hyperparameter
- Trading simulation from LSTM and classification predictions 

The first file tries to predict price using ARIMA but unable to predict small movements which
led to using LSTM to predict STI. LSTM to run as univariate using closing price as variable 
and also as multivariate using technical indicators as features:
 - Exponential moving average (EMA)
 - Stochastic
 - Moving average convergence/divergence (MACD)
 - Closing price

Second file is for optimizing LSTM by using different hyperparameters

Third file runs predictions from optimized LSTM and convert to classification labels.
Labels are then combine with classification ML model for trading simulation using 2022 data.

## Optimizations

LSTM runs with the following hyperparmeter/settings:
- 50 data/steps as one input for one output
- One hidden layer
- 100 units for each layer
- 20% dropout
- Optimizer used is Adam
- Mean squared error as loss
## Prediction results
ARIMA did not give a useful prediction:
![ARIMA](https://github.com/MikoPoh/STI-prediction-using-ARIMA-and-LSTM/blob/main/Charts/ARIMA%20result.png?raw=true)

Univariate predictions:
![univariate prediction](https://github.com/MikoPoh/STI-prediction-using-ARIMA-and-LSTM/blob/main/Charts/LSTM%20univariate%20predictions.png?raw=true)

Univariate predictions:
![multivariate prediction](https://github.com/MikoPoh/STI-prediction-using-ARIMA-and-LSTM/blob/main/Charts/LSTM%20multivariate%20predictions.png?raw=true)


## Trading simulation results
Classification trading simulation:
![clf](https://github.com/MikoPoh/STI-prediction-using-ARIMA-and-LSTM/blob/main/Charts/Classification%20simulation%20trading.png?raw=true)

LSTM univariate trading simulation:
![uni](https://github.com/MikoPoh/STI-prediction-using-ARIMA-and-LSTM/blob/main/Charts/LSTM%20univariate%20simulation%20trading.png?raw=true)

LSTM multivariate trading simulation:
![multi](https://github.com/MikoPoh/STI-prediction-using-ARIMA-and-LSTM/blob/main/Charts/LSTM%20multivariate%20simulation%20trading.png?raw=true)

LSTM univariate combine with multivariate trading simulation:
![uni+multi](https://github.com/MikoPoh/STI-prediction-using-ARIMA-and-LSTM/blob/main/Charts/LSTM%20univariate%20and%20multivariate%20simulation%20trading.png?raw=true)

Classification combine with LSTM univariate trading simulation:
![clf+uni](https://github.com/MikoPoh/STI-prediction-using-ARIMA-and-LSTM/blob/main/Charts/Classification%20and%20univariate%20simulation%20trading.png?raw=true)

Classification combine with LSTM multivariate trading simulation:
![clf+multi](https://github.com/MikoPoh/STI-prediction-using-ARIMA-and-LSTM/blob/main/Charts/Classification%20and%20multivariate%20simulation%20trading.png?raw=true)

Classification combine with LSTM univariate and multivariate trading simulation:
![clf+uni+multi](https://github.com/MikoPoh/STI-prediction-using-ARIMA-and-LSTM/blob/main/Charts/Classification%20and%20univariate%20and%20multivariate%20simulation%20trading.png?raw=true)







## Lessons Learned

The project was built to complement what classification machine learning model lacked in.
More LSTM layers or units built may not give better or closer prediction. Adding of features
do not give better predictions.

LSTM predictions tend to lag actual price by a bit, by combining with classification 
ML noise from both model are reduced to give an overall improvement.

