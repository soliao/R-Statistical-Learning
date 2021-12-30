# Ch2. Statistical Learning

## The Bias-Variance Trade-Off

*Expected test MSE* = Var(f) + [Bias(f)]^2 + Var(irreducible error)

Var(f): Variance. The amount by which f would change if we use a different training data set to estimate it

Bias(f): Bias. The error that is introduced when we approximate a more complicated real-life problem by a simpler model


## The Bayes Classifier

For classifications problems, the test error rate is minimized by assign the class Y = j to X = x_i if Prob(y = j | X = x_i) is maximum among all classes.

The Bayes classifier produces the lowest possible test error rate (Bayes error rate)

To use the Bayes classifier, we need to know the **conditional distribution of Y given X** - P(Y|X)

If the true distribution is known, Bayes calssifer is not available. Substitution: KNN (need to choose K)

- Smaller K:  smaller bias, larger variance
- Larger K: larger bias, smaller variance
