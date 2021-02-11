# Ch.8 Tree-Based Methods

## Regression Trees

**Recursive binary splitting**\
Greedy approach - take the best split that yields the greatest decrease in RSS/error rate

**Tree pruning**\
Tune the parameter *alpha* (increasing from 0), find the subtree that minimizes
```
E = sum_RSS_from_each_leaf + alpha * |T|
```
Different values of *alpha* will return subtrees with different sizes, the optimal subtree can be obtained by cross-validation

## Classification Trees

Cost functions:

1. *Classification error rate*\
  Fraction of training observations in a region (m) that do not belong to the most common class (k).
  ```
  error rate = 1 - proportion_of_the_most_common_class
  ```
  
2. *Gini index*\
  Total variance across all K classes. A measure of **purity** (the smaller Gini index -> more purity of the classification in the region)\
  ```
  Gini = sum_over_k{p_k*(1-p_k)} 
  ```
  
3. *Entropy*\
  ```
  entropy = - sum_over_k{p_k*log(p_k)}
  ```
  
The **Gini index** and **entropy** are more sensitive to the **node purity**

## Pros/Cons of Trees

Pros: easy for visualization and handle qualitative variables\
Cons: not robust - small change in data can greatly change the fitted tree\
Improvements: **bagging**, **random forests**, and **boosting**

## Bagging

Idea: reduce variance by averaging over multiple set of samples (bootstrapping to get more training sets)
```
1. Use bootstrapping to generate B training sets
2. Fit each training set with a decision tree (and obtain B trees) without pruning (so that each tree has a higher variance but lower bias)
3. Regression: use the average prediction to predict on the test data
   Classification: take the majority vote from the B trees
```
Using large B won't cause over-fitting

**Out-of-bag error (OOB)**\
On average, 1/3 of the training data are not sampled by a round of bootstrapping. For each training data x_i, about B/3 trees didn't use it.\
We can use those B/3 to predict on that out-of-bag data x_i to obtain the average OOB MSE/OOB classification error rate to estimate the test error.

**Variable importance**\
*Regression*\
Mean decrease in the RSS when splitting over that variable\
*Classification*\
Mean decrease in the Gini index when splitting over that variable

## Random Forests

Idea: **decorrelate** the trees. During every split, *only a random sample of m variables* are considered as candidates. m = sqrt(p)

Reasoning: without random forests, most correlating features will always be picked. Occasionally this strong features will be blocked 
to be used by the algorithm so that bagged trees will look less similar. Averaging over *less correlated* bagged trees can better reduce
the variance.

## Boosting

Idea: bagged trees are grown **sequentially**

- each tree is small (stump: single split)
- each tree is grown using the residuals from the previous tree
- learning is kept slow by using a shrinkage parameter

Boosting will overfit if B is too large
