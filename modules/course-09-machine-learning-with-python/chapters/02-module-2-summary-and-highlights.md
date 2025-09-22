# Course 9, Module 2: Summary and Highlights

## Overview
This module covers regression techniques for modeling relationships between features and a continuous target, from simple and multiple linear regression to nonlinear and logistic regression, including training concepts like OLS, log-loss, and gradient descent.

## Linear Regression
- Simple linear regression: one independent variable predicts a dependent variable via a best-fit line that minimizes Mean Squared Error (MSE) using Ordinary Least Squares (OLS).
- Multiple linear regression: extends to multiple predictors to model outcomes and analyze variable relationships.
- Considerations: OLS is interpretable but sensitive to outliers; adding too many variables risks overfitting—perform careful feature selection.

## Nonlinear Regression
- Use polynomial, exponential, or logarithmic functions when relationships are not linear.
- Polynomial regression can increase flexibility but may overfit by capturing noise rather than true patterns.

## Logistic Regression
- Probabilistic binary classifier suitable for binary targets and feature impact assessment.
- Trained by minimizing log-loss; optimized with gradient descent or stochastic gradient descent for efficiency.
- Gradient descent iteratively minimizes the cost function during training.

## Applications
- Forecasting sales, estimating maintenance costs, predicting rainfall, modeling disease spread, and more.

## Takeaways
- Start with linear models; watch for outliers and overfitting.
- Choose nonlinear or logistic models when assumptions of linearity or target type require it.
- Use gradient-based optimization to efficiently train logistic regression.

