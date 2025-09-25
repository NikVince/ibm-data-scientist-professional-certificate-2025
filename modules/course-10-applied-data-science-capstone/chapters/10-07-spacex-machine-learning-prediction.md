# SpaceX Machine Learning Prediction Model

**Reference:** `completed_assignements/10-07-spacex-machine-learning-prediction.ipynb`

## Overview
This lab focused on creating a comprehensive machine learning pipeline to predict SpaceX Falcon 9 first stage landing success. The goal was to develop and compare multiple classification algorithms to identify the best-performing model for landing prediction.

## Key Objectives
- Create binary classification labels for landing success
- Standardize the data for machine learning
- Split data into training and testing sets
- Find optimal hyperparameters for multiple algorithms
- Compare model performance and select the best approach

## Data Preparation

### Dataset Loading
- **Target Data:** `dataset_part_2.csv` (binary classification labels)
- **Feature Data:** `dataset_part_3.csv` (engineered features)
- **Target Variable:** Binary classification (1 = successful landing, 0 = failed landing)

### Data Preprocessing
- **Target Creation:** `Y = data['Class'].to_numpy()`
- **Feature Standardization:** `StandardScaler()` for normalization
- **Train-Test Split:** 80% training, 20% testing with `random_state=2`
- **Test Set Size:** 18 samples for validation

## Machine Learning Algorithms Tested

### 1. Logistic Regression
**Implementation:** `LogisticRegression()` with GridSearchCV
- **Hyperparameters:** C=[0.01, 0.1, 1], penalty='l2', solver='lbfgs'
- **Cross-Validation:** 10-fold CV
- **Best Parameters:** C=0.01, penalty='l2', solver='lbfgs'
- **Validation Accuracy:** 84.64%
- **Test Accuracy:** 83.33%

**Confusion Matrix Analysis:**
- **True Positives:** 12 (correctly predicted successful landings)
- **False Positives:** 3 (incorrectly predicted successful landings)
- **Performance:** Good at identifying successful landings

### 2. Support Vector Machine (SVM)
**Implementation:** `SVC()` with GridSearchCV
- **Hyperparameters:** kernel=['linear', 'rbf', 'poly', 'sigmoid'], C=logspace(-3,3,5), gamma=logspace(-3,3,5)
- **Cross-Validation:** 10-fold CV
- **Best Parameters:** C=1.0, gamma=0.0316, kernel='sigmoid'
- **Validation Accuracy:** 84.82%
- **Test Accuracy:** 83.33%

**Performance:** Similar to Logistic Regression with slightly higher validation accuracy

### 3. Decision Tree Classifier
**Implementation:** `DecisionTreeClassifier()` with GridSearchCV
- **Hyperparameters:** criterion=['gini', 'entropy'], splitter=['best', 'random'], max_depth=[2*n for n in range(1,10)], max_features=['sqrt'], min_samples_leaf=[1,2,4], min_samples_split=[2,5,10]
- **Cross-Validation:** 10-fold CV
- **Best Parameters:** criterion='gini', max_depth=8, max_features='sqrt', min_samples_leaf=4, min_samples_split=5, splitter='random'
- **Validation Accuracy:** 87.50%
- **Test Accuracy:** 61.11%

**Performance:** High validation accuracy but poor test performance (overfitting)

### 4. K-Nearest Neighbors (KNN)
**Implementation:** `KNeighborsClassifier()` with GridSearchCV
- **Hyperparameters:** n_neighbors=[1-10], algorithm=['auto', 'ball_tree', 'kd_tree', 'brute'], p=[1,2]
- **Cross-Validation:** 10-fold CV
- **Best Parameters:** algorithm='auto', n_neighbors=10, p=1
- **Validation Accuracy:** 84.82%
- **Test Accuracy:** 83.33%

**Performance:** Consistent with Logistic Regression and SVM

## Model Performance Comparison

### Final Results
| Algorithm | Validation Accuracy | Test Accuracy | Performance |
|-----------|-------------------|---------------|-------------|
| Logistic Regression | 84.64% | 83.33% | **Best** |
| SVM | 84.82% | 83.33% | **Best** |
| Decision Tree | 87.50% | 61.11% | Poor (overfitting) |
| KNN | 84.82% | 83.33% | **Best** |

### Best Performing Methods
- **Logistic Regression:** 83.33% test accuracy
- **SVM:** 83.33% test accuracy  
- **KNN:** 83.33% test accuracy

**Winner:** Logistic Regression (selected as best due to simplicity and interpretability)

## Key Findings

### Model Performance
- **Consistent Performance:** Three algorithms achieved identical test accuracy
- **Overfitting Issue:** Decision Tree showed high validation but poor test performance
- **Robust Results:** Multiple algorithms converged to similar performance levels

### Confusion Matrix Insights
- **True Positives:** 12 successful landings correctly predicted
- **False Positives:** 3 failed landings incorrectly predicted as successful
- **Error Pattern:** Model tends to be optimistic (predicts success more often)

### Hyperparameter Optimization
- **Logistic Regression:** Low C value (0.01) indicates preference for simpler models
- **SVM:** Sigmoid kernel with moderate C and gamma values
- **Decision Tree:** Moderate depth (8) with regularization parameters
- **KNN:** 10 neighbors with Manhattan distance (p=1)

## Business Impact

### Cost Prediction Accuracy
- **83.33% Accuracy:** Reliable prediction of landing success
- **Cost Implications:** Successful prediction enables accurate launch cost estimation
- **Competitive Advantage:** $62M vs $165M launch cost difference

### Model Interpretability
- **Logistic Regression:** Most interpretable for business stakeholders
- **Feature Importance:** Clear understanding of factors affecting success
- **Decision Making:** Reliable predictions for launch planning

## Technical Achievements

### Data Pipeline
- **Standardization:** Proper feature scaling for algorithm compatibility
- **Train-Test Split:** Appropriate data partitioning for validation
- **Cross-Validation:** Robust hyperparameter optimization

### Algorithm Comparison
- **Multiple Approaches:** Tested 4 different classification algorithms
- **Hyperparameter Tuning:** GridSearchCV for optimal parameter selection
- **Performance Evaluation:** Comprehensive accuracy and confusion matrix analysis

### Model Selection
- **Best Practice:** Selected model based on test performance, not validation
- **Overfitting Detection:** Identified and avoided overfitted models
- **Interpretability:** Chose Logistic Regression for business value

## Output
- **Best Model:** Logistic Regression with 83.33% test accuracy
- **Hyperparameters:** C=0.01, penalty='l2', solver='lbfgs'
- **Confusion Matrix:** Detailed performance analysis
- **Feature Importance:** Understanding of success factors

## Recommendations

### Model Deployment
- **Production Ready:** Logistic Regression model ready for deployment
- **Monitoring:** Track performance on new launch data
- **Retraining:** Regular model updates with new launch data

### Business Application
- **Launch Planning:** Use predictions for cost estimation
- **Risk Assessment:** Factor in landing success probability
- **Competitive Analysis:** Understand SpaceX's cost advantage

This machine learning phase successfully created a reliable prediction model for SpaceX landing success, providing valuable insights for cost estimation and competitive analysis in the commercial space industry.
