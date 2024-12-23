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

|R&D Spend|	Administration|	Marketing Spend|	State	|Profit| Florida | New York|
|----------|---------------|----------------|-------|-------|--------|--------|
|165349.2|	136897.8|	471784.1|	New York|	192261.83| ..     | ..     | ..     |
|162597.7	|151377.59	|443898.53	|Florida	|191792.06| ..     | ..     | ..     | 
|153441.51|	101145.55|	407934.54|	New York|	191050.39| ..     | ..     | ..     | 
|144372.41	|118671.85	|383199.62	|Florida	|182901.99| ..     | ..     | ..     | 
|142107.34|	91391.77|	366168.42|	Florida|	166187.94| ..     | ..     | ..     | 
|131876.9	|99814.71	|362861.36	|New York	|156991.12| ..     | ..     | ..     | 

 + 3. Assign numeric values to each category; for the case of two; 0 and 1

|R&D Spend|	Administration|	Marketing Spend|	State	|Profit| Florida | New York|
|----------|---------------|----------------|-------|-------|--------|--------|
|165349.2|	136897.8|	471784.1|	New York|	192261.83| 0 | 1 |
|162597.7	|151377.59	|443898.53	|Florida	|191792.06| 1 | 0 |
|153441.51|	101145.55|	407934.54|	New York|	191050.39| 0 | 1 |
|144372.41	|118671.85	|383199.62	|Florida	|182901.99| 1 | 0 |
|142107.34|	91391.77|	366168.42|	Florida|	166187.94| 1 | 0 |
|131876.9	|99814.71	|362861.36	|New York	|156991.12| 0 | 1 |

 + 4. Hence, our formula takes the dummy variable (D) for computation
      
    y = b0 + b1*x1 + b2*x2 + b3*x3     + b4*D4
   
   __Note__: we include only the Florida column because, if Florida is one, 0 will mean it is New York, hence, no lost of data. (no need to include b5*D5). Dummy variables work like light switches (On/Off). when you have D as 0, the entire equation swtiches to New York as the b0 coefficient automatically become for the D=0
   
## Dummy Variable Trap: 
> The Dummy Variable Trap is a scenario that occurs when dummy variables are included in a regression model in such a way that it leads to multicollinearity, causing issues in the estimation of regression coefficients. It happens when the number of dummy variables used exceeds the necessary amount, creating a perfect correlation between one or more dummy variables.

## Why does the Dummy Variable Trap occur?
> When you create dummy variables to represent a categorical variable with k categories, you generally only need k - 1 dummy variables. This is because when you have 
𝑘−1 dummies, the last category is implicitly represented by the absence (i.e., all zeros) of the other dummies.

> If you use k dummy variables instead of k - 1, the regression model will have perfect multicollinearity. This means one of the dummy variables can be predicted perfectly using the others, leading to redundancy and violating the assumption of no perfect multicollinearity in regression models.
> 
> Dummy variable occur when you add the two variable into the equation. It means you are duplicating the variable because
> e.g b4*D1 +  b5*D2, here, D5 = 1-D2, hence causing duplication.

## You cannot have these three elements in a formula at the same time
> ### b0 +..... b4D1 + b5D4 (that is the contant and both the dummy variable)
