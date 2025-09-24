# Course 9, Module 5: Summary and Highlights

## Overview
This module covers model evaluation, validation, and common pitfalls across supervised, unsupervised, and dimensionality reduction tasks. You learned key metrics, cross-validation strategies, regularization, and practices to avoid overfitting and data leakage.

## Supervised Evaluation
- Train/test splits estimate generalization to unseen data.
- Classification metrics: accuracy, confusion matrix, precision, recall, F1 (balances precision and recall).
- Regression metrics: MAE, MSE, RMSE, R-squared, explained variance.

## Unsupervised and Dimensionality Reduction
- Unsupervised metrics: Silhouette Score, Davies–Bouldin Index, Adjusted Rand Index (external labels).
- Dimensionality reduction evaluation: Explained Variance Ratio, Reconstruction Error, Neighborhood Preservation.

## Validation and Regularization
- Validation sets and test sets help tune hyperparameters while preventing overfitting.
- Cross-validation (k-fold, stratified) enables robust estimates without overfitting to the test set.
- Regularization: Ridge (L2) and Lasso (L1) add penalties to reduce overfitting in linear models.

## Pitfalls and Best Practices
- Prevent data leakage by strict train/validation/test separation and careful feature engineering.
- Watch for class imbalance, misleading feature importance, and over-reliance on automation without causal reasoning.
- Interpret feature importance cautiously considering redundancy, scale, and non-causality.

## Takeaways
- Choose metrics aligned with the problem (classification vs regression).
- Use cross-validation and regularization to generalize better.
- Guard against leakage and misinterpretation to build trustworthy models.

