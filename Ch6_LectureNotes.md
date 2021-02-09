# Ch6. Linear Model Selection and Regularization


## Ridge regression and lasso

**Bayesian intepretation**

Assume the coefficients beta has a prior distribution p(beta) = g(beta_1)\*g(beta_2)\*...\*g(beta_p)

1. If g is a Gaussian distribution with mean 0 and standard deviation a function of *lambda*, then the posterior **mode** and **mean** for *beta* is given by the ridge regression solution

2. If g is a Laplace (double-exponential) distribution with mean 0 and scale parameter a function of *lambda*, then the posterior **mode** for *beta* is given by the lasso solution

## Dimension reduction

**Principle component regression**

- The 1st principle component direction is along that there is the greatest variability in the data

**Partial lease squares**
