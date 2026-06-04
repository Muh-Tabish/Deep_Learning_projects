# Heart Disease Prediction Using a Feedforward Neural Network

## Overview

This project implements a Feedforward Neural Network (FNN) using PyTorch to predict whether a patient has heart disease based on clinical features from the UCI Heart Disease Dataset.

The objective is to classify patients into two categories:

* No Heart Disease (0)
* Heart Disease Present (1)

The project demonstrates the complete deep learning workflow, including data preprocessing, feature scaling, model training, and evaluation.

---

## Dataset

The dataset contains approximately 300 patient records with 13 clinical features and 1 target variable.

### Features

* Age
* Sex
* Chest Pain Type (cp)
* Resting Blood Pressure (trestbps)
* Cholesterol (chol)
* Fasting Blood Sugar (fbs)
* Resting ECG (restecg)
* Maximum Heart Rate (thalach)
* Exercise-Induced Angina (exang)
* Oldpeak
* Slope
* Number of Major Vessels (ca)
* Thalassemia (thal)

### Target Variable

Original Target Values:

* 0 = No Heart Disease
* 1–4 = Presence of Heart Disease

Converted Binary Labels:

* 0 = No Heart Disease
* 1 = Heart Disease Present

---

## Data Preprocessing

The following preprocessing steps were performed:

1. Imported the dataset using Pandas.
2. Checked for missing values.
3. Removed invalid or missing records.
4. Converted the target variable into binary labels.
5. Standardized input features using StandardScaler.
6. Split the dataset into:

   * Training Set (80%)
   * Validation Set (10%)
   * Testing Set (10%)

---

## Model Architecture

The Feedforward Neural Network consists of:

| Layer          | Configuration      |
| -------------- | ------------------ |
| Input Layer    | 13 Features        |
| Hidden Layer 1 | 32 Neurons + ReLU  |
| Hidden Layer 2 | 16 Neurons + ReLU  |
| Output Layer   | 1 Neuron + Sigmoid |

### Network Structure

```text
13 Input Features
        │
        ▼
Hidden Layer 1
(32 Neurons, ReLU)
        │
        ▼
Hidden Layer 2
(16 Neurons, ReLU)
        │
        ▼
Output Layer
(1 Neuron, Sigmoid)
        │
        ▼
Binary Prediction
(Heart Disease / No Heart Disease)
```

### Hyperparameters

* Optimizer: Adam
* Learning Rate: 0.001
* Loss Function: Binary Cross Entropy Loss (BCELoss)
* Batch Size: 16
* Epochs: 50

---

## Results

### Model Performance

| Metric            | Value                |
| ----------------- | -------------------- |
| Training Accuracy | ~88%                 |
| Testing Accuracy  | **87.10%**           |
| Loss Function     | Binary Cross Entropy |
| Optimizer         | Adam                 |
| Learning Rate     | 0.001                |
| Epochs            | 50                   |

### Classification Metrics

| Class           | Precision | Recall | F1-Score |
| --------------- | --------- | ------ | -------- |
| No Disease      | 0.93      | 0.76   | 0.84     |
| Disease Present | 0.76      | 0.93   | 0.84     |

Overall Testing Accuracy: **87.10%**

---

## Visualizations

The project includes:

* Training vs Validation Loss Curve
* Confusion Matrix Heatmap
* Classification Report

These visualizations help evaluate model performance and identify possible overfitting.

---

## Technologies Used

* Python
* PyTorch
* NumPy
* Pandas
* Matplotlib
* Seaborn
* Scikit-learn

---

## Project Structure

```text
Heart-Disease-Prediction/
│
├── heart.csv
├── heart_disease_prediction.ipynb
├── best_model.pth
├── README.md
└── results/
    ├── loss_curve.png
    └── confusion_matrix.png
```

---

## Conclusion

A Feedforward Neural Network was successfully developed to predict heart disease using clinical patient data. After preprocessing and training, the model achieved a testing accuracy of 87.10%, which exceeds the expected performance threshold for this assignment. The results demonstrate that deep learning can effectively classify heart disease using tabular medical datasets.

---

