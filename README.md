# Walmart-Sales-Prediction

Predict weekly sales using 10-fold-cross-validation 

train.csv: 5 columns ("Store", "Dept", "Date", "Weekly_Sales", "IsHoliday") ranging from 2010-02 to 2011-02.

test.csv: 7 columns ("Store", "Dept", "Date", "IsHoliday", "Weekly_Pred1", "Weekly_Pred2", "Weekly_Pred3") ranging from 2011-03 to 2012-10 with the last three columns being zero.

fold_1.csv, ..., fold_10.csv: 5 columns ("Store", "Dept", "Date", "Weekly_Sales", "IsHoliday") and one for every two months starting from 2011-03 to 2012-10.

## Precessing:
1. Reformat the data into weekly time series per store within a department then loop over
every department.
2. Append the forecasting result for two months from 2011-03 to extent the training data to
forecast the next future two months for test data until the training set contain all the data.
3. Divide the training data into 10 folds in orders of the dates.

## Model 1 : Naive Model 
(Filling the missing values in training data with value 0, predict each
weekly_sales forecast using the sales of the last week)

## Model 2 : Seasonal Naive model 
(Filling the missing values in training data with value 0, predict
the future weekly_sales forecast using the sales value of the exact week of last year)

## Model 3 : Linear regression and seasonal dummy variables model 
(Filling the missing data with value 0 and make predictions using regression to model trend and seasonality of the time series
where seasonality is handled by 51 dummy variables for weekly data)
