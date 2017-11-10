---
layout: default
---

**Explorotary Data Analysis of House Price Data**

Welcome! This is a simple exploratory data analysis I performed for a house price prediction project. The data is provided by [Kaggle House Price Prediction Project](https://www.kaggle.com/c/house-prices-advanced-regression-techniques). My source code can be accessed through [Github](https://github.com/Jianwei-Bao/HousePricePrediction).
<!-- and, _italic_, or ~~strikethrough~~. --> 

### [](#header-3)Dataframe

This Dataframe contains 1460 rows and 81 columns. Here is the head of the dataframe.

|Id| MSSubClass| MSZoning| LotFrontage| LotArea|	Street|	...| MoSold|	YrSold| SaleType|	SaleCondition|	SalePrice|
|:-|:----------|:--------|:-----------|:-------|:------|:---|:------|:------|:--------|:-------------|:---------|
|	1|         60|	      RL|        65.0|    8450|   Pave|	...|      2|   2008|	      WD|	       Normal|    208500|
|	2|         20|       RL|        80.0|    9600|   Pave|	...|      5|   2007|	      WD|	       Normal|    181500|
|	3|         60|       RL|        68.0|   11250|   Pave|	...|	     9|   2008|       WD|	       Normal|	   223500|
| 4|         70|       RL|        60.0|    9550|   Pave|	...|      2|   2006|       WD|	      Abnorml|    140000|
|	5|         60|	      RL|        84.0|   14260|   Pave|	...|     12|   2008|       WD|       Normal	|    250000|


### Missing Values
 
I started with checking missing values in the dataset. There are several columns contain over 90% missing values, we can probably exclude those columns in our regression model. They are "Alley", "PoolQC", "Fense", and "MiscFeature".

![](https://github.com/Jianwei-Bao/HousePricePrediction/blob/master/Part%201%20plotly%20graphs/msno.png?raw=true)
 
### Variables
The distribution of dependent variable is left skewed.
![](https://github.com/Jianwei-Bao/HousePricePrediction/blob/master/part%202%20graphs/sales%20distribution.PNG?raw=true)
![](https://github.com/Jianwei-Bao/HousePricePrediction/blob/master/part%202%20graphs/uniqs.PNG?raw=true)

By looking at the number of unique values, we know that most of the variables are categorical because they have unique values less than 100. A good way to examine the effect of different categories on the sales price is to plot scatter or box plots to see if there is a relationship. Let's check a few of them.
 
![](https://github.com/Jianwei-Bao/HousePricePrediction/blob/master/Part%201%20plotly%20graphs/housestyle.PNG?raw=true) 
![](https://github.com/Jianwei-Bao/HousePricePrediction/blob/master/Part%201%20plotly%20graphs/mssub.PNG?raw=true)
![](https://github.com/Jianwei-Bao/HousePricePrediction/blob/master/Part%201%20plotly%20graphs/neighborhood.PNG?raw=true)
![](https://github.com/Jianwei-Bao/HousePricePrediction/blob/master/Part%201%20plotly%20graphs/yearbuilt.PNG?raw=true)

### Correlation Matrices

Let's see how the numerical variables are correlated with each other and with the dependent variable. There are quite a few variables that are strongly correlated with "SalePrice", I ploted the scatter matrices of top three variables.
![](https://github.com/Jianwei-Bao/HousePricePrediction/blob/master/part%202%20graphs/corr.PNG?raw=true)
![](https://github.com/Jianwei-Bao/HousePricePrediction/blob/master/part%202%20graphs/scatter.PNG?raw=true)

### Feature Importances
Using default XGB regressor and Random Forest Regressor to identify key features. Categorical features are relabeled with numerical values. Missing values are replaced with mean values so they do not have impacts to the model.

![](https://github.com/Jianwei-Bao/HousePricePrediction/blob/master/part%202%20graphs/xgbft.PNG?raw=true)
![](https://github.com/Jianwei-Bao/HousePricePrediction/blob/master/part%202%20graphs/RFft.PNG?raw=true)

The top features selected by both models are somewhat different. This would require us to dig deeper into the data. This page will be updated regularly as I make progress.

Well, thank you for reading the post :)


