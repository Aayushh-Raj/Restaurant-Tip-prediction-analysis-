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

ANOVA
| 	|df|	MS|	F|	Significance F|
|---|---|---|---|---|
|Regression|	6|	36.37951327	|34.91579067|	4.09922E-30|			
|Residual|	237|	1.041921508|	 |	 |			
|Total|	243|   |   |   |	 	 	 			
							
|   |	Coefficients | t Stat	|P-value | Lower 95%|	Upper 95%| Lower 95.0%|	Upper 95.0%|
|----|----|----|----|----|----|----|----|
|Intercept|	0.822484874|	2.557503833|	0.011166488	|0.188931591|	1.456038157|	0.188931591|	1.456038157|
|size|	0.174819618|	1.960142606|	0.051150876|	-0.000881295|	0.350520531|	-0.000881295|	0.350520531|
|total_bill|	0.094325088|	9.889219168|	1.57818E-19|	0.075534657|	0.113115518	|0.075534657	|0.113115518|
|sex|	-0.034644964|	-0.245566218|	0.806230561|	-0.312579818|	0.24328989|	-0.312579818|	0.24328989|
|smoker|	-0.075663089|	-0.539686293|	0.589920088|	-0.351857061|	0.200530884	|-0.351857061|	0.200530884|
|day	|-0.05273982|	-0.4382763|	0.661585219	|-0.289801948|	0.184322308|	-0.289801948|	0.184322308|
|time|	0.112477769	|0.365750277	|0.714877667|	-0.493356099|	0.718311636|	-0.493356099	|0.718311636|

After inspecting the p-value of each independent variables, the ones which had p-value > 0.15 were not significant in predicting the tip variable. So independent variables such has sex, smoker, day and time really didn’t had any impact on predicting the tip. So I excluded those variables and re-run the regression tool.

### SUMMARY OUTPUT 2

|Regression Statistics|  |
|:----|:-----|
|Multiple R	|0.684009729|
|R Square	|0.467869309|
|Adjusted R Square|	0.463453286|
|Standard Error|	1.013505967|
|Observations	|244|

ANOVA
| 	|df|	MS|	F|	Significance F|
|---|---|---|---|---|
|Regression|	2|108.82932	|105.9481301|	9.66509E-34|			
|Residual|	241|	1.027194344|	 |	 |			
|Total|	243|   |   |   |	 

|   |	Coefficients | t Stat	|P-value | Lower 95%|	Upper 95%| Lower 95.0%|	Upper 95.0%|
|----|----|----|----|----|----|----|----|
|Intercept|	0.668944741|	3.455126549	|0.000649806	|0.287562197|	1.050327285	|0.287562197|	1.050327285|
|size|	0.192597794	|2.25750214|	0.024872446|	0.024540385|	0.360655204|	0.024540385|	0.360655204|
|total_bill|	0.092713337|	10.17186688|	1.88092E-20|	0.074758723|	0.110667951|	0.074758723|	0.110667951|

This improved the statistics of prediction model for the tip and so the formula to predict tip based on above stats is as follows,

##     (predicted tip) = Intercept + (Coefficient of size) x (Size variable) + (Coefficient of total bill) x (total bill variable)
##                                  Y = 0.67 + 0.19 (Size variable) + 0.09 (Total bill variable)

I applied this formula in excel on a predicted tip column to generate the predicted tip.
Next, I did calculate the RMSE metric for the model using excel and the result is as follows,

|Sum of error^2 |	247.553837|
|:----|:-----|
|Count of errors|	244|
|RMSE|	1.007256127|

So with a RMSE value of approximately 1 we can say the model is pretty good in predicting the tip.
Lastly, I plotted a line graph depicting predicted vs actual tip using  excel.

![graph]()

