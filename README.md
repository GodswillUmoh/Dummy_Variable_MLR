# Dummy_Variable_MLR
## Handling Dummy Variable in Multiple Linear Regression (MLR)
> A dummy variable is a numerical variable used in regression analysis and other statistical models to represent categories or groups. Dummy variables are often used to encode categorical data into a numerical format so that it can be incorporated into mathematical models.

# Building_Multiple_Linear_Regression_Model with Dummy Variable
> Note: The Dataset used here was got from SuperDataScience Training on Machine Learning.
> The First Seven records of the Sample Dataset is displaced below for insight into the data

## The Dataset: It contains 50 Startups, displaying their expenditure in different areas as seen in the table.
|R&D Spend|	Administration|	Marketing Spend|	State	|Profit|
|----------|---------------|----------------|-------|-------|
|165349.2|	136897.8|	471784.1|	New York|	192261.83|
|162597.7	|151377.59	|443898.53	|Florida	|191792.06|
|153441.51|	101145.55|	407934.54|	New York|	191050.39|
|144372.41	|118671.85	|383199.62	|Florida	|182901.99|
|142107.34|	91391.77|	366168.42|	Florida|	166187.94|
|131876.9	|99814.71	|362861.36	|New York	|156991.12|

## Summary of Dataset:
> Profit is the dependent variable. The investor wants to see if there is a correlation between the expenditure on the predictors (independent) and the outcome (profit). In the dataset, we see a categorical column, State. The task will be converting it into the dummy variaable.
> 
> From the table we can form a multiple linear regression formula:
> y = b0 + b1x1 + b2x2 + b3x3 + ??? (no value in state column)

## Steps To Creating Dummy Variables
+ 1. Check the column to know how many categories you have (in our dataset, we have two; New York, Florida)
+ 2. For every single category, you create a new column
|R&D Spend|	Administration|	Marketing Spend|	State	|Profit| Florida | New York
|----------|---------------|----------------|-------|-------|--------|--------|
|165349.2|	136897.8|	471784.1|	New York|	192261.83| | |
|162597.7	|151377.59	|443898.53	|Florida	|191792.06| | |
|153441.51|	101145.55|	407934.54|	New York|	191050.39| | |
|144372.41	|118671.85	|383199.62	|Florida	|182901.99| | |
|142107.34|	91391.77|	366168.42|	Florida|	166187.94| | |
|131876.9	|99814.71	|362861.36	|New York	|156991.12| | |
  4. 
