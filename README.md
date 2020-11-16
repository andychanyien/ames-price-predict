# DSI17_Project2_Ames

## Problem Statement

As a seller, wouldn't it be ideal to know how much your property would fetch? What about knowing how else you could increase the value of your property? As a buyer, wouldn't it be insightful to know which characteristics to look out for in a property when you wish to buy it as an investment?

The Ames, Iowa, Housing dataset has a wide range of information collected from 2006 to 2010 by the Ames Assessor's Office, which was used to assess the value of residential properties sold in Ames. It contains 80 specific characteristics describing the basement, garage, above ground area, the lot, the surroundings and the roof, including the quality, condition and the materials used.

Based on the above dataset, a predictive model will be created based on regression - using Lasso, Ridge, Linear or ElasticNet regression - to determine which characteristics would affect the sale price the most. Through exploratory data analysis (EDA), this notebook will explore the relationship between the different variables and the sales price. Variables which have the highest positive correlation and highest negative correlation will be used to build and train the predictive model. The type of regression to use will also be determined by comparing at least 3 regression metrics and through cross validation score. After a model is selected, the largest positive and negative coefficients will identify the characteristics which influence sale price the most.

It will then conclude with recommendations which sellers could consider to increase the value of their home. Similarly, buyers can also look into the characteristics which will allow them to buy at a lower value and sell it at a higher value in future.

## Executive Summary

During the EDA, the relationship between each variable and sale price was examined closely. The dataset collected was rather extensive and was useful to help identify general trends. However, there are also many collinear features which potentially complicates regression. Hence, with domain knowledge on the dataset, certain variables were removed while some were combined. New variables were also created to combine collinear variables to avoid overfitting. There were many null values but all of them could be imputed through either a linear regression or through deduction. The summary of the findings can be found below:

**Findings:**
- The general trend is that the higher the quality and the condition, the higher the sale prices
- The larger the area, the higher the sale prices
- The more unfinished parts, the lower the sale prices
- Certain materials also fetched higher sale prices than others
- Properties which are sold more recently and are newer tend to fetch higher prices

**Model Evaluation and Selection**

Among Linear Regression, Lasso, Ridge and ElasticNet, a cross validation and metric comparison was done. Lasso was identified to be the most suitable based on Root Mean Squared Error (RMSE) and its R2 score. Another considation was that the model should be able to efficiently identify the essential features which affected the sale prices.

**Results**

Sellers can increase the value of their property by improving the quality and conditions of their home through renovation or refurbishing.

Meanwhile, buyers and/or investors should look out for neighbourhoods which has high property prices and perhaps buy cheap properties to resell in the future. 


## Data Dictionary

A data dictionary has been included with the dataset. [Click here](./Data%20Dictionary.txt) to view the data dictionary.

However, there are also a few engineered features which are highlighted below:

|Feature|Type|Dataset|Description|
|---|---|---|---|
|**total_sf**|float|housing & housing_test|Sum of 1st floor, 2nd floor, basement 1 and basement 2 area (units in Square Feet, where 1 means 1 square feet|
|**property_age**|int|housing & housing_test|The age of the property calculated by deducting the year it was built from the year it was sold (units in years, where 20 means 20 years-old|
|**garage_int**|float|housing & housing_test|The interaction among garage features, including the condition, the area and the finishing. (area x condition x finish, where one unit in each variable will be multiplied twice)|


## Conclusions and Recommendations

In general, property prices are highly determined by the condition of the house, the quality of the materials and the area of the property. These generally influences the number of rooms, the size of the garage and other factors. Below are some other findings and recommendations to help sellers increase the value of their property based on the model.

**Features that Increases Value**

#1 Based on the model, the total area of basement and above grade (including 2nd floor) increases the value of the home the largest.

#2 The quality of the home in general also affect the prices. For example, the overall quality, the kitchen quality and the functionality of the home

#3 Being in the neighbourhood of Northridge Heights and Stone Brook also yield high sale prices

#4 New sales tend to fetch higher prices

**Features that Decreases Value**

#1 Unfinished Basement hurts the value of the home the most.

#2 Townhouse building types also decreases the value of the home.

#3 The older the property, the less value it fetches.

**For Sellers: Ensure High Sale Prices**

Based on the predictive model, here are some concerete recommendations to ensure sellers get the optimal sale price (in order of priority and highest returns):

- Refurbish the house (including rooms and kitchens) to improve the quality and the materials of the house.
- Conduct restorative works to improve and maintain the condition of the house and the materials.
- Sell the house as soon as possible, remodel or renovate the home if the home is too old.
- Finish all unfinished areas as they would decrease the value of the home.


**For Buyers: Good Investment Opportunities**

- Neighbourhoods in Northridge Heights and Stone Brook tend to have higher values. Consider buying a poorer condition home and then refurbishing it or expanding it.

- Avoid Townhouse building types as they hurt the value of houseprices. However, buyers can also consider buying up townhouses and then building a more valuable building type.

**Suggestions for Next Steps**

The model may not generalise as well to other locations or state due to how specific the features were. If we are looking at predicting the sale price in another state, similar data should be collected.

However, if the goal is to predict sale prices with higher accuracy, more years of data could be used to train the model. Another way is to expand the model with Logistic Regression to predict the likelihood of a property being sold.  