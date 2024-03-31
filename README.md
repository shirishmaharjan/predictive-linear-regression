# Predictive-linear-regression
Making linear regression model using dependent data and independent data or variable


![image](https://github.com/shirishmaharjan/predictive-linear-regression/assets/81280828/ed11a389-945b-4ca6-9bfd-47818c56b352)


# Dependent variable: Biomass (kg)
# Independent variables: Diameter (cm), Crown Width (m), 
# Age (years), Species, Soil Type, Elevation (m), 
# Canopy Cover (%), and Leaf Area Index.

# lm(y ~ x)
# lm(response_variable ~ explanatory_variable)
# lm(dependent_variable ~ independent_variable)

Dependent variable fully depend on the independent varaible. 

# Normality test 

Use ggdensity and hist to check the normality test and if the distribution is not normal that is if it is skwed to the right or left and do not have the normal distribtuion then our data set is normal. Here we can see it by just looking 

Use shapirio wilk test to check if if it normal or not , Here p value is less than 0.05 so, we can say they are not normally distributed. 

# t.test 

- It is used to compare the means of two datasets which are normally distributed. 
- Null hypothesis of t test say tha mean of two datasets are equal and alternative hyposthesis says that mean are not equal.
- If p value is less than 0.05 then we reject the null hypothesis and says that means are different.

# Mann-Whitney U test (Non parametric t test)

- It's an alternative to the t-test when the assumptions of the t-test are not met. It is used in non parametric distribution. It is used to compare the means of two datasets which are NOT normally distributed.
- A small p-value (typically less than the significance  level, often 0.05) suggests strong evidence against the  null hypothesis, indicating that the two groups have significantly different distributions

# ANNOVA 

- It is used to compare the means of three or more datasets which are normally distributed.
- If p value is less than 0.05 then we reject the null hypothesis and says that means are different.

# Log Transformation (change into normal distribution)

- The non normal distribtuion are change into normal distribtuon by using log transformation.
- basic logarithmic transformation of a number
- log(x)=loge(x)
- e = 2.71828, that is the base of the natural logarithm (Euler's number)
- 2.71828 to the power 3.54674 = 34.7 (2.71828 ^ 3.54674)
- When you apply a logarithmic transformation to your data, you're essentially taking the logarithm of each data point. This has the effect of compressing large values more than small ones, thereby reducing skewness and stabilizing variance.

# Use shapirio wilk test, ggdensity and hist to check again if our data is normally distributed or not 

# Using Linear regression

- lm(y~x)

# Multi dependent model 

- multi_variable_model <- lm(Field_height_m ~ diameter + Crown_width + Biomass..Kg., data = col_log_Data)

# Summary of the regression model
summary(multi_variable_model)
- 5e+01 means 5 * 10 to the power 1 that is 5 * 10 and whishc is 50 like this.

# Details of single variable model 

attributes(single_variable_model)
single_variable_model$residuals
hist(single_variable_model$residuals)

# Predicting it 

- Now as we have slope, intercept value we can predic the dependent variable if we have our independent variable.
- We can use slope and y intercept value in y = mx + c equation to predict the dependent variable.

col_log_Data %>% 
  lm(Field_height_m ~ diameter, data = .) %>% 
  predict(data.frame(diameter = c(2,3.5,4,4.5)))

  
