# Restaurant-Tip-prediction-analysis-
Using Predictive Analysis to predict the restaurant tip
Description:
The dataset in file Restaurant tips dataset.xlsx contains tips data for different customers. The following are the features in the dataset:
|sex |	Gender of the customer |
|:-----|:------|
|smoker |	Indicates if the customer is a smoker or not|
|day | Day of the restaurant visit|
|time	| Indicates whether the tip was for lunch or dinner|
|size |	Number of members dining|
|total bill |	Bill amount in USD|
|tip | Tip amount in USD|

The objective is to predict restaurant tips given input values (independent features) with the mathematical equation for predicting the value of the tip (dependent variable).
While performing data cleaning no empty or erroneous values were found. 
The next step I did was to encode all the independent categorical variables (sex, smoker, day and time).
Finally, I performed multiple linear regression using regression tool to generate a regression statistic as an output.

### SUMMARY OUTPUT 1
|Regression Statistics|    |
|:----|:-----|
|Multiple R|	0.684980787|
|R Square	| 0.469198679 |
|Adjusted R Square | 0.455760671|
|Standard Error	| 1.020745565|
|Observations |	244|
