# Project Title : New York Taxi Demand Prediction

![alt text](https://github.com/kushal-acharya/Data-Science-Case-Studies/blob/main/NYC%20Taxi%20Demand%20Prediction/New_york.gif)

## Problem Statement
In this case study, we will try to predict the number of pickups for yellow taxi at any given region of New York city for the next ten minutes time interval given historically collected data and data from previous time step.

The problem is a time-series forecasting problem.

The prediction results can be then transferred to taxi drivers through Smartphone app. The drivers then can subsequently move to the locations where the predicted number of pickups are high.

## Constraints

**Latency**
Some latency is acceptable, in the order of a few seconds.

**Interpretability**
The model need not be interpretable as long as the drivers are getting highly accurate results. Accuracy is of more importance than interpretability.

## Source of Data
The datasets used for this case study was collected by the NYC Taxi and Limousine Commission (TLC) and can be obtained from the following url :

https://www1.nyc.gov/site/tlc/about/tlc-trip-record-data.page

For this case study we use the data of Jan 2015 and Jan 2016. Download the data for Jan 2015 and Jan 2016 and save it in the same directory as the notebook. We will try to predict pickups for Jan 2016 and check our prediction accuracy against the original data.


## Performance metrics

This is a time-series regression problem, thus we will use the following errors as performance metrics.

1. Mean Absolute percentage error (MAPE).
2. Mean Squared error.

Here, we will focus more on Mean Absolute Percentage Error as we want the relative error in the number of pickups that we predict. Let's take an example to understand why relative error is more desirable than raw numerical error.

For this let's take two scenarios.

Scenario 1

------------
Total predicted pickups  -> 100
Actual/Correctly predicted pickups -> 94
Error -> 6

Percentage Error = 6%

Scenario 2

---------------

Total predicted pickups  -> 10
Actual/Correctly predicted pickups -> 4
Error -> 6

Percentage Error = 60%

Here, in both the cases the number of errors are same. In the first case predicting 6 extra pickups among 94 correctly predicted pickups is fine, as it doesn't impact the  overall experience/expectation of the cab driver but in the second scenario predicting that there are 10 pickups only to find 4 pickups is a very high discrepancy and affects the end user experience much.

Thus, we want to minimize the percentage / relative error not the absolute numerical error itself.




## Performance Objective

Reduce MAPE to < 12 %.

## Models used

We have tried the following models in this notebook and the best result is obtained using Xgboost Regressor when accounting for any other overfitted models.

### Baseline models
1. Simple Moving Average
2. Weighted Moving Average
3. Exponential Weighted Moving Average

### Regression models
1. Linear Regression
2. Random Forest Regressor
3. Xgboost Regressor

## Final Results

![alt text](https://github.com/kushal-acharya/Data-Science-Case-Studies/blob/main/NYC%20Taxi%20Demand%20Prediction/Final%20Results.jpg)

**Note**

For detailed understanding, kindly follow through the notebook.

The notebook uses dask dataframe instead of pandas for faster computation. Similarly, install required libraries in your environment if you encounter any error.
