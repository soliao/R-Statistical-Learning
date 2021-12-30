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
