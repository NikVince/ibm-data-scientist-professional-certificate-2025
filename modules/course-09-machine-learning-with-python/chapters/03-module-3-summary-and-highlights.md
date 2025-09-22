# Course 9, Module 3: Summary and Highlights

## Overview
This module focuses on supervised classification methods and ensemble techniques. You learned how decision trees, regression trees, k-NN, SVMs, and ensembles address different aspects of classification, along with metrics and strategies to manage bias and variance.

## Classification Basics
- Classification predicts labels on new data; applications include churn prediction, customer segmentation, loan default prediction, and multiclass drug prescriptions.
- Extend binary classifiers to multiclass via one-versus-all or one-versus-one schemes.

## Decision and Regression Trees
- Decision trees split on features at internal nodes and assign classes at leaf nodes.
- Training selects splits using criteria like Information Gain or Gini impurity; prune trees to avoid overfitting.
- Regression trees predict continuous values; split quality commonly measured by Mean Squared Error (MSE).

## k-Nearest Neighbors (k-NN)
- Assigns labels based on the closest labeled data points; supports classification and regression.
- Optimize by testing various k values and evaluating accuracy; consider class distribution and feature relevance.

## Support Vector Machines (SVM)
- Constructs a hyperplane that maximizes class margin; effective in high-dimensional spaces.
- Can be sensitive to noise and large datasets; use kernels and regularization appropriately.

## Bias–Variance and Ensembles
- The bias–variance tradeoff impacts accuracy and generalization.
- Bagging, boosting, and random forests help manage bias/variance and improve performance.
- Random forests use bagging over bootstrapped samples to train multiple trees and reduce variance.

## Takeaways
- Choose classifiers based on problem structure, data size, and feature characteristics.
- Tune k in k-NN, tree depth/pruning in trees, and C/kernel in SVMs.
- Use ensembles (bagging, boosting, random forests) to improve robustness and accuracy.

