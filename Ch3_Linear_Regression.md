# Ch3. Linear Regression

## Residual Sum of Squares (RSS)

Minimizing RSS gives the **least squares coefficient estimates** for simple linear regression

This way of estimation is unbiased


## Evaluation of the Accuracy of the Model

### Residual Standard Error (RSE)

RSE = sqrt(RSS/dof), where dof = degrees of freedom

In linear regression, RSE = sqrt(RSS/(n-2))

RSE give the **lack of fit** of the model

### R^2 Statistic

The proportion of variance explained by the model

R^2 = 1 - RSS/TSS, where TSS = total sum of squares (variance of Y)

TSS: the variability in the response before the regression is performed

RSS: the variability that remains unexplained after regression is performed

In simple linear regression, R^2 is equal to correlation^2


## Analyze Potential Problems in the Data

### 1. Non-linearity

`Why important`

Linear regression may have large bias if the reponse is not linearly dependent on the predictors.

`How to detect`

Use **Residual Plots** to see potential non-linearity in the data. Residual Plots plot **predicted values (y-hat)** on the x-axis, and **residuals (y-hat - y-true)** on the y-axis.
If a **U-shape** is observed in the residual plots, it suggests that there's non-linearlity in the data

`Solutions`

Use X^2, log(X), sqrt(X) as predictors

### 2. Correlating error terms

`Why important`

Linear regression relies on the assumption that the errors are uncorrelated

`How to detect`

1. Plot **residual** as a function of **data observations**
2. If adjacent residuals have similar values (**tracking**), the errors are correlated

`Solutions`

1. Avoid using linear regression
2. Deisign a better experiment

### 3. Error terms do not have constant variance

`Why important`

Linear regression relies on the assumption that the variance of the errors is constant across all observed data

`How to detect`

Use **Residual plots**. If the residual plot has a funnel shape, It suggests that the error terms do not have a constant variance.

`Solution`

Fit the data by **weighted least squares**, where the weight is inverse proportional to the variance

### 4. Outliers

`Why important`

Outlier may not dramatically affect the linear fit, it will increase the deteriorate the confidence interval we evaluate the coefficients of the model.

Pathway: outlier deteriorate RSE (residual standard error) --> decrease the t-statistic of the coefficient --> higher p-value --> we may not be able to reject coeff=0

`How to detect`

Use **studentized residual plots** (x = predicted values, y = studentized residuals) to detect outliers. Studentized residuals with absolute values greater than 3 are possible outliers.

`Solution`

Remove those potential outliers before performing linear fits

### 5. High leverage points

`Why important`

Data with hight leverage can affect the values of the coefficients in the linear fit.

`How to detect`

Calculate the **leverage statistic**, which will have a value between 1/n to 1. The average of the leverage statsitics of all training data is always (p+1)/n. If a data point has the leverage statistics greater than (p+1)/n, that datapoint has a high leverage.

`Solution`
Remove those potential high leverage points before performing linear fits.

### 6. Collinearity

`Why important`

Linear regression quantifies how the response is affected by the predictor indivually. If multiple predictors varies together, it's hard to separate the indicual effect of each predictor. The results of the coefficients can be very unstable and have high p-values of the t-statistics.

`How to detect`

1. Read the correlation matrix plots to detect 1-to-1 correlation
2. Cacluate the **variance inflation factor (VIF)** of each predictor. VIF is always greater than 1. If VIF is grater than 5, there may be some collinearity.

`Solutions`

1. Leave only 1 correlated predictor in the fit
2. Combine correlating predictors into 1 predictor

