# Assignment-based Subjective Questions

## From your analysis of the categorical variables from the dataset, what could you infer about their effect on the dependent variable?

- Demand of cycles increased in 2019 as compare to 2018
- People take more cycles when weather is clear
- Demand of cycles are high during summer and fall
- No major difference of bikes demand during weekdays
- Demand of cycles is high during June, July and August
- Demand of cycles is high during weekdays. It is less during holidays. We can infer that people are taking cycles for traveling to offices.
- Demand of cycles is slightly high during working days as compare to non working day

## Why is it important to use drop_first=True during dummy variable creation?

This drops the first value so that the variable can be encoded. For example, for a variable having values yes, no and maybe, if we set the dummy variable generation's attribute `drop_first=True`, only two columns will be generated with value 0 and 1. To interpret maybe (assuming it is the first column), 0,0 will be used for both columns

## Looking at the pair-plot among the numerical variables, which one has the highest correlation with the target variable?

- From the pair-plot, highest `temp` variable seems to have the highest regression
- Linear relationship exists b/w temp and atemp. This should be obvious as atemp is the Reel Feel temprature and directly propotional with temp.
- Linear relationship exists b/w cnt and temp (and atemp) as well.

## How did you validate the assumptions of Linear Regression after building the model on the training set?

- **Linear Relationship**: Pair-wise scatterplots may be helpful in validating the linearity assumption as it is easy to visualize a linear relationship on a plot.
- **Homoscedasticity**: To verify homoscedasticity, one may look at the residual plot and verify that the variance of the error terms is constant across the values of the dependent variable.
- **Absence of Multicollinearity**: Pairwise correlations could be the first step to identify potential relationships between various independent variables.
- **Independence of residuals (absence of auto-correlation)**: To verify that the observations are not auto-correlated, we can use the Durbin-Watson test. The test will output values between 0 and 4. The closer it is to 2, the less auto-correlation there is between the various variables (0–2: positive auto-correlation, 2–4: negative auto-correlation).
- **Normality of Errors**: To verify the normality of error, an easy way is to draw the distribution of residuals against levels of the dependent variable. One can use a QQ-plot and measure the divergence of the residuals from a normal distribution. If the resulting curve is not normal (i.e. is skewed), it may highlight a problem

Ref: https://towardsdatascience.com/verifying-and-tackling-the-assumptions-of-linear-regression-32126acea67b

## Based on the final model, which are the top 3 features contributing significantly towards explaining the demand of the shared bikes?

Top 3 features contributing significantly are:
- Month
- Season 
- Temprature

# General Subjective Questions

## Explain the linear regression algorithm in detail

Linear regression algorithm shows a linear relationship between a dependent (y) and one or more independent (y) variables, hence called as linear regression. Since linear regression shows the linear relationship, which means it finds how the value of the dependent variable is changing according to the value of the independent variable. The linear regression model provides a sloped straight line representing the relationship between the variables.

## Explain the Anscombe’s quartet in detail

Anscombe’s quartet comprises four datasets that have nearly identical simple statistical properties, yet appear very different when graphed. Each dataset consists of eleven (x,y) points. They were constructed in 1973 by the statistician Francis Anscombe to demonstrate both the importance of graphing data before analyzing it and the effect of outliers on statistical properties.

Ref: https://www.geeksforgeeks.org/anscombes-quartet/

## What is Pearson’s R?

In statistics, the Pearson correlation coefficient is a measure of linear correlation between two sets of data. It is the ratio between the covariance of two variables and the product of their standard deviations; thus it is essentially a normalized measurement of the covariance, such that the result always has a value between −1 and 1. As with covariance itself, the measure can only reflect a linear correlation of variables, and ignores many other types of relationship or correlation. As a simple example, one would expect the age and height of a sample of teenagers from a high school to have a Pearson correlation coefficient significantly greater than 0, but less than 1 (as 1 would represent an unrealistically perfect correlation).

Ref: https://en.wikipedia.org/wiki/Pearson_correlation_coefficient

## What is scaling? Why is scaling performed? What is the difference between normalized scaling and standardized scaling?

It is used to normalize data within particular range and is ued becasue data set contains fearures in different scale. Example; a data set can contain features like height and weight, where height of 170cm is considered as normal where as 170kg wieght is very high. In-order to subdue the effect of different scales, data is normalized.
- ** Standardization or Z-Score Normalization** is the transformation of features by subtracting from mean and dividing by standard deviation. This is often called as Z-score. `X_new = (X - mean)/Std` 
- Normalization or Min-Max Scaling is used to transform features to be on a similar scale. `X_new = (X - X_min)/(X_max - X_min)`

## You might have observed that sometimes the value of VIF is infinite. Why does this happen?

If there is perfect correlation, then VIF = infinity. This shows a perfect correlation between two independent variables. In the case of perfect correlation, we get R2 =1, which lead to 1/(1-R2) infinity. To solve this problem we need to drop one of the variables from the dataset which is causing this perfect multicollinearity.

An infinite VIF value indicates that the corresponding variable may be expressed exactly by a linear combination of other variables (which show an infinite VIF as well).

Ref: https://www.programsbuzz.com/interview-question/you-might-have-observed-sometimes-value-vif-infinite-why-does-happen

## What is a Q-Q plot? Explain the use and importance of a Q-Q plot in linear regression.

Q-Q Plots (Quantile-Quantile plots) are plots of two quantiles against each other. A quantile is a fraction where certain values fall below that quantile. For example, the median is a quantile where 50% of the data fall below that point and 50% lie above it. The purpose of Q Q plots is to find out if two sets of data come from the same distribution. A 45 degree angle is plotted on the Q Q plot; if the two data sets come from a common distribution, the points will fall on that reference line.

Ref: https://www.programsbuzz.com/interview-question/what-q-q-plot-explain-use-and-importance-q-q-plot-linear-regression