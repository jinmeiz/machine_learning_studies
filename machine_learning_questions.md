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

# Logistic classifier

1) score(xi) = w * h(xi)  (value range: -∞, +∞)
    p(y=+1| x, w) = 1 / [1 + e^(-w * h(xi) )]  (value range: 0.0, 1.0)

2) choose coefficiet w that maximizes the likehood:
    L(w) = ∏ p(yi | xi, w) 
    ln(L(w)) = y lnP + (1-y) ln(1-P)

# Gradient descent
It is slow as every update requires a full pass over data. 
For stochastic gradient descent, there are many updates for each pass.

# Gradient Boosting
loss function L(yi, F(xi))
for m = 1: M (number of trees):
    compute residual r_im = - ∂(L) / ∂F(xi)
    fit tree on gradient residuals
    compute residual region R_jm (minimize ∑L(yi, Fm-1 + r) ) ?
    new prediction: F_m(x) = F_(m-1)(x) + 𝜸 ∑ R_jm 

# Support vector machine

margin width = (X+ - X_) · w/||w|| = 2 / ||w||
maximization of width is equal to minimization of 1/2 ||w||^2

Using langrange multiplier: L =  1/2 ||w||^2 - ∑ai [yi (w · xi + b) - 1]
∂L / ∂w = 0 → w = ∑ai yi xi
∂L / ∂b = 0 → 0 = ∑ai yi 

minimizing L = ∑ai - 1/2 ∑∑ ai aj yi yj xi · xj    ➝ maximizing xi · xj
