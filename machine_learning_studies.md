# Machine Learning Notes


## Imbalanced Classification

### Why Imbalanced Classification Is Hard

- Skewed Class Distribution: most machine learning algorithms will require modification to avoid simply predicting the majority class in all cases.

- Unequal Cost of Misclassification Errors

- Dataset Size: more data provides better representation of combinations and variance of features in the feature space and their mapping to class labels. From this, a model can better learn and generalize a class boundary to discriminate new examples in the future.

- Label Noise: label noise refers to examples that belong to one class that are assigned to another class. Unmodified machine learning algorithms will define the class boundary in favor of the majority class at the expense of the minority class

- Data Distribution

## Kullback-Leibler Divergence

The Kullback-Leibler Divergence score, or KL divergence score, quantifies how much one probability distribution differs from another probability distribution. KL divergence can be calculated as the negative sum of probability of each event in P multiplied by the log of the probability of the event in Q over the probability of the event in P:

$$ KL(P||Q) = - \sum P(X) log(P(X) / Q(X)) $$

The intuition for the KL divergence score is that when the probability for an event from P is large, but the probability for the same event in Q is small, there is a large divergence. When the probability from P is small and the probability from Q is large, there is also a large divergence, but not as large as the first case.
