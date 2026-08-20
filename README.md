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





## ROC Curve

The model achieved a ROC-AUC score of **0.9533**, indicating strong ability to distinguish between High and Low performance classes.

The ROC curve visualization is available in `roc_curve.png`.

## Performance Visualization

The comparison of Accuracy, Precision, Recall, and F1-Score is available in `model_performance_metrics.png`.

## Error Analysis

The dataset contains more Low-performance observations than High-performance observations. This class imbalance can affect model performance.

The model achieved a recall of 75.69% for the High class. This means that some genuinely high-performing students were predicted as Low.

There were 79 false negatives in the test set. Reducing these errors would be important if the model were used to identify high-performing students.

## Overfitting and Generalization

The model achieved:

- **Training Accuracy:** 88.99%
- **Testing Accuracy:** 90.24%

The difference between training and testing accuracy is small. Therefore, the model does not show evidence of severe overfitting and demonstrates reasonable generalization on the test data.

### Model Limitations

Some limitations of this project are:

- Only six numerical features were used.
- Several categorical variables from the original dataset were not included in the baseline model.
- The High/Low classification depends on the chosen threshold of 70.
- A single train-test split was used for evaluation.
- The model does not establish causal relationships between student factors and performance.
- The model should be validated on an independent dataset before real-world use.

## Future Improvements

The model could be improved by:

- Including relevant categorical features.
- Using class weighting or resampling techniques to address class imbalance.
- Comparing Logistic Regression with Decision Tree and Random Forest models.
- Performing hyperparameter tuning.
- Using cross-validation for more reliable evaluation.
- Testing the model on an independent dataset.
- Considering regression if predicting the exact examination score is required.

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Jupyter Notebook

## Project Files

```text
Week-4-Machine-Learning/
│
├── README.md
├── Week_4_ML_Development.ipynb
├── confusion_matrix.png
├── model_performance_metrics.png
└── roc_curve.png
