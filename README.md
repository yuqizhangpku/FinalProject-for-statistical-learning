# FinalProject-for-statistical-learning
Course project for statistical learning(House Prices: Advanced Regression Techniques(Kaggle))

Introduction

Nowadays, people are more likely to choose which house to buy based on more and more aspects. However, when we ask a home buyer to describe their dreamhouse, it is not so likely that they begin with the hight of the basement ceiling or the proximity to an east-west railroad. Important as these factors are sometimes, there are some relationship which could not be easily observed when faced with realistic problem. Here I would like to build the model of a prediction model of house price. This project aims at solving a problem about the prediction of the house price based on the dataset provided on Kaggle. The dataset includes 80 variables of which most are discrete variables. After giving overall summary of it, I transfer these discrete ones into numerical variables and explore the relationship between them. Then use dierent regression models to predict the result.

Data Preprocessing:

There are three important steps in data preprocessing:

1. Based on the analysis above, it is obvious that most of the variables are categorical variables. Here I would like to conform most of them into numeric ones.
2. At the same times, there are some outliers, for example, there are a few houses with more than 4,000 square living area. This is not applicable so we drop them from the train dataset.
3. Some data are missing so we fill in the blanks with mode, median or average according to the type of the variable. 

Here I will only give the process of preprocessing. Detailed explanation will be found in the python file.

1. Considering the realistic problems, not so many people will buy enormous house. So here we exclude the records where GrLivArea > 4000.
2. After transferring the whole dataset into a dataframe, during which I also fill in some blanks with modes, I try to turn the categorical features into ordinal numbers. (Function factorize could be found in codes) Here come the detailed steps:
(a) Transform some specific factors(such as ExterQual) into numbers. (e.g. PO, Fa, TA, Gd, Ex into 0, 1, 2, 3, 4, 5)
(b) Transform binary variables into (0,1), such as Has2ndFloor and LsRegularLotShape.
(c) Simplify the existing numerical features: such as change SimpleOverallQual into a variable with only two types.
(d) Transform neighborhood into feature.
3.Considering the scale of the sale price, I also deal with the price with log
function so that it could be normalized.
4.Finishing all the steps above, I transform categorical features into one-hot
encoding, through which the number of variables will be enriched. For
example, if there is a variable with m possible values, it will be transformed
into m variables with value 0 or 1. As a result, the data matrix will be more
sparse.

Model and Result
After preprocessing the dataset, I mainly use two models; Lasso and XGboost based on Python. Finally I use the average of results derived these two methods and the best result is rank 98(first 5%)
