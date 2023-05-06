# FM_MLfinalProject.github.io
MAP 6114 Machine Learning UWF Final Project

I have worked on the hospital data from the CORGIS Dataset Project. This dataset provides hospitals performance measure information related to heart attack, emergency department care, preventive care, stroke care, and other conditions. The data is part of an Administration-wide effort to increase the availability and accessibility of information on quality, utilization, and costs for effective, informed decision-making.
 
It has 24 columns, among which 4 are regarding location, 8 are related to various rating status, the rest are some information about heart attack, pneumonia and hip-knee procedures.
I have decided to model heart attack cost procedure using other information present in this dataset. I wanted to see if there is any indication about how much a heart attack procedure will cost based on its location,  ratings or facility type.
 
## Mid Project: 
First, since procedure cost is a continuous variable, I used linear regression for modeling. For independent variables I tried various rating measures, to see if a facility's rating can predict the heart attack procedure cost, or if they do, which ones would be most significant.
 
First, I loaded the data, then for data pre-processing, I looked at our dependent variable for possible outlier, or discrepancy. From the histogram it is evident that there are lots of rows with values around 0 for this column. It may be possible that the cost information for those facilities are not present, or presented incorrectly. In any case, we have to get rid of them to find proper predictors.
I filtered the column to keep values ranging from 18000.

![cost before](https://github.com/[FarihaUpoma]/[FM_MLProject]/blob/[main]/cost_a.png?raw=true)
![cost after](https://github.com/[FarihaUpoma]/[FM_MLProject]/blob/[main]/cost_b.png?raw=true)


Next, I looked at the rating measures, I saw that the values are presented as how they stand against the national average. The possible values are the same, above, or below. Among them, a significant amount of rows consists of None value, so I needed to filter these out too.
The variables we are using as predictors are all categorical in nature. For linear regression using scikit-learn, we need to have number values in the predictors. So, I created dummy variables for the model.
 
We want to predict how much a heart attack procedure will cost, so this will be our dependent variable.
 
For splitting the data into a train and test set, I did a 70-30 split.
 
I created a linear regression model and fit the data on training sets. After that, I used the model to predict the test dataset.
 
The r^2 value is used to evaluate the performance of a regression-based machine learning model. It is the coefficient of determination. It works by measuring the amount of variance in the predictions explained by the dataset. The higher the R^2 values, the better the model fit data.



Based on the results, we see that the model is not a good model. From the model summary, we can also see that no rating measures come out as significant for an alpha value=0.05.
 
The other information presented in the database are location and facility type. I tried to see if the facilities' type and location could be good indicators for a procedure cost.
 
After following the same steps of linear regression for the new predictors, I generated the R^2 value.
 
The two linear regression models have significantly different R-squared values. The first model, with safety rating and experience rating as predictors, has a very low R-squared value of 3.66%, indicating that only a small portion of the variation in the cost of heart attack procedures is explained by these variables. On the other hand, the second model, with facility type and location as predictors, has a much higher R-squared value of 76%, indicating that a large portion of the variation in the cost of heart attack procedures can be explained by these variables.
 
The 2nd model showed better results than the 1st one. So, the city where the hospital is located, and whether it is government owned, private or proprietary.
 
The data I picked is not that informational unfortunately. However, more analysis is possible based on the procedure related information. Due to time limitations, I have to conclude my report here.

