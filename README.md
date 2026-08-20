# Week 4 - Machine Learning Model Development and Evaluation

## Project Overview

This project was completed as part of the Week 4 technical internship task on Machine Learning Model Development and Evaluation.

The objective of this project is to develop and evaluate a basic machine learning classification model using Python and Scikit-learn. The Student Performance Factors dataset was used to classify students into High and Low performance categories.

## Dataset

The Student Performance Factors dataset contains 6,607 student records and 20 original features related to academic performance, attendance, study habits, resources, and other student factors.

### Target Variable

A new binary target variable called `Performance` was created using `Exam_Score`:

- **High:** Exam Score >= 70
- **Low:** Exam Score < 70

### Class Distribution

| Performance | Count |
|-------------|------:|
| Low | 4,982 |
| High | 1,625 |

## Data Preprocessing

The following preprocessing steps were performed:

1. Loaded the dataset using Pandas.
2. Checked data types and missing values.
3. Handled missing values using mode imputation for categorical columns.
4. Created the binary `Performance` target variable.
5. Selected relevant numerical features.
6. Split the dataset into training and testing sets.
7. Standardized the numerical features using `StandardScaler`.

### Selected Features

- Hours_Studied
- Attendance
- Sleep_Hours
- Previous_Scores
- Tutoring_Sessions
- Physical_Activity

## Machine Learning Algorithm

### Logistic Regression

Logistic Regression was selected because it is a simple and interpretable classification algorithm suitable for binary classification problems.

It was used to classify students into:

- High Performance
- Low Performance

## Model Training

The dataset was divided into:

- **80% Training Data**
- **20% Testing Data**

A `random_state` of 42 was used to make the experiment reproducible.

## Model Evaluation

The trained model was evaluated using Accuracy, Precision, Recall, F1-Score, Confusion Matrix, and ROC-AUC.

### Results

| Metric | Score |
|--------|------:|
| Accuracy | 90.24% |
| Precision | 83.11% |
| Recall | 75.69% |
| F1-Score | 79.23% |
| ROC-AUC | 95.33% |

### Training vs Testing Accuracy

- **Training Accuracy:** 88.99%
- **Testing Accuracy:** 90.24%

The small difference between training and testing accuracy indicates that the model does not show severe overfitting.

## Confusion Matrix

The confusion matrix was:

```text
[[947, 50],
 [79, 246]]
