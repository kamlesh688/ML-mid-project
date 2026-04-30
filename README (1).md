# Machine Learning Midterm Project (Student Performance Prediction)

## Project Overview

This project is a supervised machine learning classification task that predicts whether a student will pass or fail based on academic and personal information. A real-world dataset of 395 samples is used from the UCI Machine Learning Repository (Student Performance Dataset).

## Objective

* Load and use a real-world CSV dataset
* Perform Exploratory Data Analysis (EDA)
* Visualize data patterns
* Apply supervised learning models
* Compare model performance
* Evaluate accuracy and analyze results

## Dataset Description

The dataset contains 395 records with the following features:

* school — Student's school (GP or MS)
* sex — Student's gender (F or M)
* age — Student's age (15 to 22)
* address — Home address type (Urban or Rural)
* studytime — Weekly study time (1 to 4)
* failures — Number of past class failures
* absences — Number of school absences
* Medu — Mother's education level
* Fedu — Father's education level
* G1 — First period grade
* G2 — Second period grade
* G3 — Final grade (used to create target)
* passed — Target Variable (0 = Fail, 1 = Pass) → G3 >= 10 means Pass

**Dataset Source:** UCI Machine Learning Repository
**Download Link:** https://raw.githubusercontent.com/guipsamora/pandas_exercises/master/04_Apply/Students_Alcohol_Consumption/student-mat.csv

Note: G1 and G2 columns are dropped before training to avoid data leakage.

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn

## Exploratory Data Analysis (EDA)

The following steps were performed:

* Data inspection using `.info()` and `.describe()`
* Checking missing values (dataset has no missing values)
* Visualizing class distribution (Pass vs Fail)
* Feature distribution histograms for Pass vs Fail students
* Correlation heatmap to identify important features
* Box plots comparing key features across pass/fail groups

## Machine Learning Models Used

### 1. Logistic Regression

* Simple linear classification model
* Requires feature scaling (StandardScaler applied)
* Works well when decision boundary is linear
* Highly interpretable — coefficients show feature impact
* Used as a strong and reliable baseline model

### 2. Random Forest Classifier

* Ensemble of 150 decision trees
* Handles non-linear relationships between features
* Does not require feature scaling
* Provides feature importance scores
* More complex model — prone to overfitting on small datasets

## Evaluation Metrics

* Accuracy Score (Train and Test separately)
* Train vs Test Accuracy Comparison (Overfitting Check)
* Precision, Recall, F1 Score
* Cross-Validation Score (5-Fold)
* Confusion Matrix
* Metrics Comparison Bar Chart

## Results Summary

| Metric | Logistic Regression | Random Forest |
|---|---|---|
| Train Accuracy | ~90% | ~100% |
| Test Accuracy | ~88% | ~82% |
| Precision | ~91% | ~82% |
| Recall | ~84% | ~82% |
| F1 Score | ~87% | ~82% |
| CV Score | ~88% | ~83% |

* Logistic Regression achieved higher test accuracy (88%) with a very small train-test gap (~2%), showing no overfitting
* Random Forest achieved 100% training accuracy but dropped to 82% on test data — a gap of 18% which indicates overfitting
* Logistic Regression is the better performing and more stable model for this dataset

## Conclusion

This project demonstrates how different machine learning models behave on the same dataset. Logistic Regression performed better because the student pass/fail decision boundary is mostly linear — it depends on a weighted combination of features like study time, absences, and prior grades. Random Forest was too complex for the dataset size (395 records) and overfit the training data. This project highlights the trade-off between model complexity (Random Forest) and simplicity with stability (Logistic Regression).

## How to Run the Project

1. Open Google Colab
2. Run Step 1 first to import all libraries
3. Run Step 2 to load the dataset directly from URL
4. Run all remaining steps in order
5. Observe EDA, training, and results
6. Compare model performance in final summary

## Project Structure

```
ML-Student-Project/
│── notebook.ipynb
│── README.md
```

## Author

YOUR NAME HERE
```
Replace YOUR NAME HERE with your actual name before submitting.
```
