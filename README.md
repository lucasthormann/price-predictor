#  Quantum Computing Companies Stock Prices
Andrew Guilette, Lucas Thormann

## Project Summary
In this project, we used multiple machine learning algorithms to predict stock prices. We tweaked the alpha values in each regression to find out how the alpha value impacted each regression and what values led to better models.

We found that the Ridge Regression led to a small mean squared error and an R2 score close to 1. The Lasso Regressions had a higher mean squared error than the Ridge Regressions did and a slightly lower R2 score. We concluded that the Ridge Regressions performed better due to the multicollinearity of the dataset which is common in stock data.

## Problem Statement 
Our objective is to design then evaluate a model capable of predicting future share prices of predominant, publicly traded companies on the NASDAQ Stock Market, centered around quantum computing technologies. Our data is derived from publicly available resources which consistently index daily share price volatility/movement of all companies listed on the NASDAQ Stock Market. The resulting model may provide insight into market trends surrounding this emerging industry.


## Dataset 
https://www.kaggle.com/datasets/nourajo/quantum-computing-companies-stock-data
The dataset is 136,518x7 with columns representing date, opening price, high, low, closing price, adj close, volume, and ticker. The data spans multiple years for over a dozen companies.

<Complete for May 2nd submission. What Processing Tools have you used.  Why?  Add final images from jupyter notebook. Use questions from 3.4 of the [Datasheets For Datasets](https://arxiv.org/abs/1803.09010) paper for a guide.>  


## Exploratory Data Analysis 
We will use scatter plots to show data over the time span for each feature. We will also use box plots to show the spread of data within each feature.

We explored multiple types of regressions that we could use on the datasets and settled on using both Ridge regression and Lasso regression.

## Data Preprocessing 
We trimmed the dataset down to represent three tickers, dropped any null values from the dataset, and used the min max scaler to scale the dataset. After further exploration, we decided that we would use all the associated data of a single company in order to develop our models. Due to Google's data being robust and it's trend line being relatively homogenous we chose it to focus on.

## Machine Learning Approaches
Since similar technology exist, we researched which models have proven to be most successful in predicting stock futures. This led us to choose the Ridge regression and the Lasso regression as they are often used to analyze stock values. Ridge regression works well to train models involving stocks as they are affected by multicollinearity. Multicollinearity indicates that collinear indepenndent variables are realated in some fashion, although the relationship may or may not be casual. For example, past performance might be related to market capitalization, as stocks that have performed well in the past will have increasing market values.

## Experiments
We conducted experiments to find the best alpha value and max iterator value by manipulating the alpha values in the Ridge regression models and the max iterator values in the Lasso regression models. We evaluated our solutions using the mean squared error and the R2 score. 
We decided to compare the results of our models using their R2 score and the MSE.

The r2 score varies between 0 and 100%. R2 Score can be defined as the (total variance explained by model) / (total variance). So, if it is 100%, the two variables are perfectly correlated, i.e., with no variance at all. A low value would show a low level of correlation, meaning a regression model that is not valid, but not in all cases.

Mean square error (MSE) is the average of the square of the errors. The larger the number the larger the error. Error in this case means the difference between the observed values y1, y2, y3, … and the predicted ones pred(y1), pred(y2), pred(y3), … We square each difference (pred(yn) – yn)) ** 2 so that negative and positive values do not cancel each other out. 

Changing the alpha value in the Lasso regression did not work to change the mean squared error or the R2 score. 
