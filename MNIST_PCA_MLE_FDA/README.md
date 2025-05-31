# MNIST Classification with PCA, LDA, and QDA

## Overview

This project involves classification of handwritten digits (0, 1, and 2) from the MNIST dataset using various statistical techniques including:

- Maximum Likelihood Estimation (MLE)
- Principal Component Analysis (PCA)
- Linear Discriminant Analysis (LDA)
- Quadratic Discriminant Analysis (QDA)
- Fisher’s Discriminant Analysis (FDA)

## Dataset

- **Source**: MNIST dataset in `.idx` format.
- **Preprocessing**:
  - Images flattened from (28x28) to 784-dimensional vectors.
  - Normalized to the range [0, 1].
  - Subsampled 100 samples per class (0, 1, 2) for both training and test sets.

## Components

### 1. MLE (Maximum Likelihood Estimation)

- MLE estimates of mean and covariance were computed for each class.
- Used Gaussian likelihood to classify test samples.
- **Results**:
  - **Train Accuracy**: 93.0%
  - **Test Accuracy**: 92.33%

---

### 2. PCA (Principal Component Analysis)

- PCA applied to reduce dimensionality while retaining:
  - **95% variance** → ~52 components
  - **90% variance** → ~49 components
  - **2 components only** for visualization
- Eigen decomposition used on the covariance matrix.

---

### 3. LDA and QDA on PCA-transformed data

#### With 95% retained variance:
- **LDA**:
  - Train Accuracy: 99.33%
  - Test Accuracy: 94.66%
- **QDA**:
  - Train Accuracy: 100%
  - Test Accuracy: 89.66%

#### With 90% retained variance:
- **LDA**:
  - Train Accuracy: 98%
  - Test Accuracy: 96%
- **QDA**:
  - Train Accuracy: 100%
  - Test Accuracy: 93%

#### With only 2 PCA components:
- **LDA**:
  - Train Accuracy: 91%
  - Test Accuracy: 88%
- **QDA**:
  - Train Accuracy: 93.33%
  - Test Accuracy: 91.66%

---

### 4. FDA (Fisher Discriminant Analysis)

- Computed between-class and within-class scatter matrices.
- Projected data to 2D space (since C-1 = 2 for 3 classes).
- Applied LDA and QDA on FDA-reduced data.

#### Results:
- **LDA on FDA**:
  - Train Accuracy: 93%
  - Test Accuracy: 92.33%
- **QDA on FDA**:
  - Train Accuracy: 95.66%
  - Test Accuracy: 95%

---

### 5. Visualization

- 2D scatter plots created for both PCA and FDA projected data.
- Color-coded by class to demonstrate separability.

## How to Run

Ensure you have:
- MNIST `.idx` files in correct paths
- Python packages:
  - `numpy`
  - `matplotlib`
  - `scipy`

## Conclusion

- PCA significantly reduces data dimensionality while preserving important variance.
- LDA performs better with linear boundaries, while QDA adapts well to class-specific covariances.
- FDA explicitly maximizes class separability and works well with both LDA and QDA.
