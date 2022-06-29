## Multiple Linear Regression for Predicting Car Prices
The aim of this project is to develop a multi linear regression model for predicting car prices with the available independent variables. This will allow the management to understand how the prices will vary with the independent variables and allow them to manipulate the design of the cars and business strategy to meet certain price levels.

## Exploring the data

The nummerical variables are plotted against each other using seaborn pair plot to observe relationships among all the features

<img src="https://github.com/karthikramx/Multiple-Linear-Regression-for-Predicting-Car-Prices/blob/main/Images/sns_pair_plot.png" alt="drawing"/>

#### Observations
1. The distribution of prices is not normal and a log transformation could improve the model performance
2. Compresion ration has outliers in the data 
3. There seem to be a lot of correlated variables which might lead to the problem of multicollinearity

## Data preparation 
1. The price data which is the target variable is skewed and a log transformation is applied to transform the data into a normal distribution.
2. Categorical variables are transformed to dummy variables and numerical variables.
3. Data is normalized and split into train and test sets

<img src="https://github.com/karthikramx/Multiple-Linear-Regression-for-Predicting-Car-Prices/blob/main/Images/Distribution%20of%20price%20and%20log%20price.png" alt="drawing"/>

The heat maps of the all the feature correlation is observed below 

<img src="https://github.com/karthikramx/Multiple-Linear-Regression-for-Predicting-Car-Prices/blob/main/Images/heatmap_corr.png" alt="drawing"/>


## Model Building

The following steps were followed to build the model
1. The linear regression model summary on the train data is observed along with VIF (Variance inflation factor)
2. As there are a lot of variable to eliminate using p-value and VIF, RFE (Recursive feature elimination) is utilized to select the most significant features with least colleration with other features. 
3. Both manual and automated feature elimination is employed to tune the model on the train set

<p float="left" align="center">
<img src="https://github.com/karthikramx/Multiple-Linear-Regression-for-Predicting-Car-Prices/blob/main/Images/lr%20summary.png" alt="drawing"     style="width:608px;"/>

<img src="https://github.com/karthikramx/Multiple-Linear-Regression-for-Predicting-Car-Prices/blob/main/Images/VIF.png" alt="drawing" style="width:200px;"/>
</p>


## Residual Analysis

<p float="left" align="center">
<img src="https://github.com/karthikramx/Multiple-Linear-Regression-for-Predicting-Car-Prices/blob/main/Images/t1%20dist.png" alt="drawing"     style="width:400px;"/>

<img src="https://github.com/karthikramx/Multiple-Linear-Regression-for-Predicting-Car-Prices/blob/main/Images/t1%20dist.png" alt="drawing" style="width:400px;"/>
</p>


## Improvements to the model

As the test set R-squared is not similar to the train set r-squared the following changes can be implemented to improve the model performance
1. Drop colinear variables
2. Explore and drop ourliers in the data set
3. Tranform features with skewed distribution
4. Apply Principla component analysis to improve model performance for feature elimination
