# AUC/AUROC

- AUC: area under the curve
- AUROC: area under the receiver operating characteristic curve

Reference: https://stats.stackexchange.com/questions/132777/what-does-auc-stand-for-and-what-is-it

# Normalization

It involves subtracting mean and deviding variance. By normalizing features, cost function will be more round (more spherical contours, then wherever we start gradient descent can go straight to the minimum), and thus easier to optimize. On the other side, if features have different ranges, gradients can oscillate back and forth, and take a long time. 
