# AUC/AUROC

- AUC: area under the curve
- AUROC: area under the receiver operating characteristic curve

Reference: https://stats.stackexchange.com/questions/132777/what-does-auc-stand-for-and-what-is-it

# Normalization

It involves subtracting mean and deviding variance. By normalizing features, cost function will be more round (more spherical contours, then wherever we start gradient descent can go straight to the minimum), and thus easier to optimize. On the other side, if features have different ranges, gradients can oscillate back and forth, and take a long time.

# Why neural network

To acheive high performance, we need train a big neural network to take advantage of large data.

# Sigmoid function vs. rectified linear unit (Relu) function

When using sigmoid functions, there are regions where gradient is nearly zero (parameters change very slowly), and thus learning becomes slow. For Relu function, gradient is equal to one for all positive input values. By switching to Relu function can make gradietn descent work much faster.

# Attention model

Attention model computes a set of attention weights and determine how much you should pay attenton to different parts of inputs.

$\alpha^{<t, t'>}$: amonut of attention $y^{<t>}$ (output at t step) should pay to $a^{<t'>}$ (RNN features from t step)
    

# Transfer learning

It refers to a process where a model trained on one problem is used in some way on a second, related problem. Pre-trained models can be used as classifier, feature extractor (layers of pre-trained model are frozen during training), weight initilization (layers are trained during training).

# Kullback-Leibler Divergence

The Kullback-Leibler Divergence score, or KL divergence score, quantifies how much one probability distribution differs from another probability distribution. KL divergence can be calculated as the negative sum of probability of each event in P multiplied by the log of the probability of the event in Q over the probability of the event in P:

$$$ KL(P||Q) = - \sum P(X) log(P(X) / Q(X))$

The intuition for the KL divergence score is that when the probability for an event from P is large, but the probability for the same event in Q is small, there is a large divergence. When the probability from P is small and the probability from Q is large, there is also a large divergence, but not as large as the first case.

