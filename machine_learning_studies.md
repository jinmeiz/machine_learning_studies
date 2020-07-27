# Machine Learning Notes


## Imbalanced Classification

### Why Imbalanced Classification Is Hard

- Skewed Class Distribution: most machine learning algorithms will require modification to avoid simply predicting the majority class in all cases.

- Unequal Cost of Misclassification Errors

- Dataset Size: more data provides better representation of combinations and variance of features in the feature space and their mapping to class labels. From this, a model can better learn and generalize a class boundary to discriminate new examples in the future.

- Label Noise: label noise refers to examples that belong to one class that are assigned to another class. Unmodified machine learning algorithms will define the class boundary in favor of the majority class at the expense of the minority class

- Data Distribution
