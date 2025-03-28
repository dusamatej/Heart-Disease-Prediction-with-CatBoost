# Heart-Disease-Prediction-with-CatBoost
Analyzing and Predicting Heart Disease in Patients Using UCI Dataset

Overview

This project explores different classification approaches for predicting heart disease using the CatBoost algorithm. The dataset originates from the UCI Heart Disease dataset, and models are trained using different target variable structures, including 5-class, 3-class, 3-class with SMOTE, and 2-class models. Additionally, SHAP (SHapley Additive Explanations) and PCA (Principal Component Analysis) are implemented to enhance interpretability and feature selection. The goal is to assess how modifying the number of target classes and performing feature evaluation impacts classification accuracy and recall, particularly for severe heart disease cases.
#
Dataset

The dataset consists of medical features such as age, cholesterol levels, blood pressure, and other risk factors associated with heart disease. The target variable represents the severity of heart disease on a scale of 0 to 4, where 0 indicates no heart disease, and 4 represents the most severe case.

#
Models Trained

1. Five-Class Model (Original Target Variable)

Accuracy: 62.5%

Severe cases were frequently misclassified, with Class 4 achieving an F1-score of 0.00.

The model struggled due to class imbalance and difficulty distinguishing fine-grained severity levels.

2. Three-Class Model (Merging Classes 1-2, 3-4)

Accuracy: 66.85%

Some improvement in overall accuracy, but Class 2 (Severe Heart Disease) still had poor recall (0.22).

Merging similar severity levels helped reduce misclassification but still favored majority classes.

3. Three-Class Model with SMOTE (Balancing the Data)

Accuracy: 72.87%

Major improvement in classification balance across all classes.

Class 2 (Severe Heart Disease) recall increased from 0.22 to 0.78, meaning the model correctly identified more severe cases.

Demonstrates the effectiveness of oversampling minority classes in medical classification problems.

4. Two-Class Model (Binary Classification: No Heart Disease vs. Heart Disease)

Accuracy: 84.78%

Best overall performance, with Class 1 recall reaching 0.89, ensuring most heart disease cases were correctly identified.

Simplifies classification but loses medical granularity, as it no longer distinguishes between mild and severe cases.

#
Feature Evaluation

SHAP (SHapley Additive Explanations) Analysis

SHAP was used to interpret feature importance in the model.

Most influential features:

'cp' (chest pain type)

'exang' (exercise-induced angina)

'oldpeak' (ST depression induced by exercise)

'slope', 'age', and 'thal' also played significant roles.

The insights from SHAP helped in refining feature selection and improving model explainability.

PCA (Principal Component Analysis) for Feature Reduction

PCA was applied to reduce dimensionality and analyze feature variance.

The cumulative variance plot showed that a subset of principal components could explain most of the dataset’s variance.

This technique can be used to speed up model training while retaining essential information.

#
Key Insights

Reducing the number of classes increases accuracy but reduces clinical usefulness.

SMOTE effectively improves recall for minority classes and prevents the model from being biased toward majority classes.

SHAP helps interpret model predictions, ensuring medically relevant features are prioritized.

PCA can be used to optimize model performance by reducing dimensionality.

A binary classification model is best for general heart disease screening, but a multi-class model with SMOTE provides more diagnostic insight.

Future improvements could include hierarchical classification, where a binary model first identifies heart disease cases, followed by a secondary model to classify disease severity—thus balancing accuracy and medical relevance.


#
Future Improvements

Hyperparameter tuning to further optimize CatBoost performance.

Feature engineering to add medically relevant features.

Exploring alternative models such as XGBoost, LightGBM, or neural networks.

Testing the impact of PCA on predictive performance.
