# used_cars_prices
Descripition of price calculation for different used cars
The purposes of the dataset is to support different companies define the price of sale for similar cars in a secondary market. 

Sales of used cars is a market with many suppliers and customers and the pricing of vehicles 
can be complicated due to lack of comparable or extras available for the models. The data set 
available in Kaggle can be used to support price determination to some types of vehicles 
based on the characteristics available in our dataset. 

Notice that characteristics not available in our dataset can not be used to predict the price of a 
car based on our model. If someone wants to know if the price of the car will be affected by 
the number of owners, this can not be answered, because the dataset does not provide this 
variable and therefore does not calculate a model to include this variable. The dataset does 
not have information about brands like Land Rover, Aston Martin or Ferrari, therefore it shall 
not be used to predict sales for vehicles from these Brands, because the accuracy is going to 
be very low.

## USE LINEAR MODEL ##

This section is reserved for the Linear Regression Model analysis, which was done after the 
EDA Analysis in my workbook, because the EDA is very important to help understand, see 
and take decisions about our dataset on different aspects: outliers, missing values, duplicates, 
exclusion. These decisions will help generate a more robust data set where we can implement 
the appropriate linear model. 

First step is to divide the treated dataset in two files, one with the dependent numerical
variable (price), while the other file has the independent variables (all other variables). Both 
files should have the same number of rows, but not the same number of columns. Afterwards, 
the file with the dependent variables need to be transformed : categorical variables should be 
transformed in numerical values for calculations.

Once the dummy variables for categories are created it is possible to split the data between 
training and test. This split shall be done randomly in order to avoid concentration of some 
characteristics in one of them (train or test sets). The training set must have the higher 
number of rows, because it is where the model is built and needs to be "colorful" & "strong" 
enough to support different sets.

To define a linear regression you need to use the package ‘from sklearn.linear_model import 
LinearRegression’, define a name for your linear regression and apply on training set. Check 
the level of accuracy for the training and test set (adjusted R²). If the accuracy in the training 
set is much higher than the accuracy in the test set, it means your model is overfitting and not
useful for any other data rather than the training set. It is very important to have similar levels 
of accuracy on training and test set, because it will confirm the capacity of your model to 
work in different environments (different datasets). Our model has a very high accuracy both 
in training and test set, which is very positive. 

Once the model has been implemented in another dataset (different than our test & training 
sets) it is also possible to check its accuracy again.

A detailed overview of the OLS summary can confirm some insights we had on EDA 
Analysis. We can see that many variables have a “p-value” above 0.05, which is a threshold 
for statistical significance of the variable. As mentioned in the correlation matrix, if the 
variables explain the same thing, the model will be able to calculate this and the “p-value” for 
the less relevant variable will be above 0.05. In our case there are several of them. 
Regarding the p-values of the categorical variables, the also have many “p-value” above 0.05. 
This situation in category “make” show that some cars Brands are more relevant for price 
definition than others (positive or negative). Notice that the brands like BMW, Mercedes, 
Porsche, Peugot have “p-value” lower than 0.05 which will surely affect their price level. In 
the case of high level cars this influence my increase the price, while the popular brands like 
Peugot may have negative price influence. The positive or negative influence is not define in 
“p-value”.

The coefficients calculated by the OLS Summary will be used to define the equation to 
calculate future prices of cars. Below is our Equation:
Charge = ( 36.67463556711399 ) * wheel-base + ( -24.34516512708014 ) * length + ( 
749.0851624949117 ) * width + ( 3.9513159248621506 ) * curb-weight + ( 
218.38912538318215 ) * engine-size + ( -15504.501074006848 ) * bore + -
2381.15238421773

Once the model is finished, it is important to check its predictions accuracy with the test set.
Below are some metrics of the errors made during the predictions.
A graphical view can also give more insights about the differences, the values further apart
from the trend line in scatter plot have the highest mistakes. In the distribution plot, the
values on the left side of the normal curve have higher mistakes compared to the ones in the 
normal curve.
 
