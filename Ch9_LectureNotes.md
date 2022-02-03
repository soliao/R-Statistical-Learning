# Ch9 Support Vector Machines

1. Finding a hyperplane that separate the data well, in the meantime allowing some violations to the separation.

2. Using a kernel (a measure of similarity between observations) to expand the feature space to accommodate non-linear class boundaries

3. Kernels are picked so that computation can be reduced to pair-wise observation computations


## Maximal Margin Classifier

A hyperplane (p-1 dimensional subspace) divides the p-dimensional space into two halves.

## Support Vector Classifier

Support vector classifier allows some violations. It uses **soft margins** by setting a severity limit for separation violations.

In support vector classifier, only a subset of the observations (support vectors) affects the location of the hyperplane

## Support Vector Machine

Support vector machine enlarges the feature space to generate non-linear decision boundaries. Feaure space is enlarged by using some special kernels (ex. polynomial kernels and radial kernels).

## SVM and Logistic Regression

Linear-kernel SVM (a.k.a. support vector classifier) is equilivant to minimize the **hinge loss** plus the **L-2 penalty of the weight beta's**

The hinge loss of SVC is similar to the logistic regression loss.
