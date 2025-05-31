# Decision Trees, Bagging, and Random Forests

## Overview

This notebook demonstrates the implementation and comparison of three popular machine learning algorithms for classification:

- **Decision Trees (DT)**
- **Bagging (Bootstrap Aggregating)**
- **Random Forests (RF)**

The models are evaluated on a sample dataset, and their training accuracy, testing accuracy, and variance are compared to analyze their performance and generalization capabilities.

---

## Dataset

- A synthetic or preloaded dataset is used (e.g., from `sklearn.datasets`).
- Features and labels are split into training and testing sets using `train_test_split`.

---

## Implemented Models

### 1. Decision Tree Classifier

- A single Decision Tree is trained.
- Default scikit-learn classifier used: `DecisionTreeClassifier()`
- **Metrics Computed**:
  - Training Accuracy
  - Test Accuracy

### 2. Bagging Classifier

- An ensemble of Decision Trees trained on bootstrapped samples.
- Implemented using `BaggingClassifier` with base estimator as Decision Tree.
- **Hyperparameters**:
  - Number of estimators (trees): typically 100
- **Metrics Computed**:
  - Training Accuracy
  - Test Accuracy

### 3. Random Forest Classifier

- Ensemble of Decision Trees using random subsets of features at each split.
- Implemented using `RandomForestClassifier`.
- **Hyperparameters**:
  - Number of trees: typically 100
  - `max_features` set to `sqrt(n_features)` or similar
- **Metrics Computed**:
  - Training Accuracy
  - Test Accuracy

---

## Variance Estimation

- The **variance** of the predictions across multiple models (in Bagging and RF) is calculated.
- Helps demonstrate how ensembles reduce variance compared to a single decision tree.

---

## Results Summary

| Model             | Train Accuracy | Test Accuracy | Variance Reduced? |
|------------------|----------------|---------------|-------------------|
| Decision Tree     | High           | Lower         | No               |
| Bagging           | High           | Higher        | Yes              |
| Random Forest     | High           | Highest       | Yes (Best)              |

> Note: Exact values depend on the dataset and random seed.

---

## Conclusion

- **Decision Trees** tend to overfit, resulting in high training accuracy but poor generalization.
- **Bagging** significantly improves test accuracy and reduces overfitting by aggregating predictions.
- **Random Forests** further improve performance by adding feature-level randomness, which reduces correlation between individual trees.

---

## Requirements

- Python 3.x
- Libraries:
  - `numpy`
  - `pandas`
  - `matplotlib`
  - `seaborn`
  - `sklearn`

To install missing packages:
```bash
pip install numpy pandas matplotlib seaborn scikit-learn
