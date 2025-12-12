# breast-cancer-classification
Machine learning project for predicting breast cancer tumors as benign or malignant using multiple algorithms.
# Breast Cancer Classification – Machine Learning Project

## Project Objective

The objective of this project is to analyze the **Breast Cancer Wisconsin (Diagnostic)** dataset and predict whether a breast tumor is **Benign** or **Malignant** using multiple machine learning algorithms.  
The project aims to compare and analyze model behavior, the impact of **data preprocessing, normalization, hyperparameter tuning**, and **overfitting** across different models.

---

## Dataset

* **Dataset Name:** Breast Cancer Wisconsin (Diagnostic)  
* **Source:** UCI Machine Learning Repository  

This dataset contains features extracted from breast tumor images, and each sample has a binary label:

* **M:** Malignant  
* **B:** Benign

---

## Project Workflow

### Data Preprocessing

The following preprocessing steps are applied:

* Removing unnecessary features such as the `id` column  
* Checking and handling missing values  
* Standardizing features using **StandardScaler** (especially important for KNN and AdaBoost)  
* Converting labels to numerical values (e.g., M=1 and B=0)  

### Splitting Data into Train and Test Sets

The data is split into **80% training** and **20% testing** sets using `train_test_split` to ensure accurate model evaluation.

### Model Building and Training

The following models are implemented and evaluated:

* **Decision Tree Classifier**  
  * Criteria: `gini` and `entropy`  

* **K-Nearest Neighbors (KNN)**  
  * Tested with K values: 3, 5, 7  

* **Random Forest Classifier**  
  * Number of trees: 100 and 200  

* **AdaBoost Classifier**  
  * Number of estimators: 50 and 100  

---

## Model Evaluation

The performance of models is assessed using the following metrics:

### Accuracy

Indicates the overall correctness of the model in predicting samples accurately.

### Precision

Measures the correctness of the model’s predictions for the Malignant class.

### Recall

A critical metric in medical applications; indicates how many **actual malignant cases** are correctly identified.

### F1-Score

A balanced measure of Precision and Recall, especially suitable for imbalanced datasets.

### Confusion Matrix

Displays the number of correct and incorrect predictions for each class.

Comparison and Conclusion

---

### Best Recall: Random Forest (n_estimators=100)

### Highest Accuracy: Random Forest (n_estimators=100)

### Overfitting Analysis:

Overfitting was evaluated using three strict criteria:

Train Accuracy > 0.97

Accuracy Gap (Train vs Test) > 0.05

Cross-Validation (CV) Mean < Train Accuracy by more than 0.05

Findings:

Overfitted Models: Both Decision Tree configurations (Gini and Entropy) overfit, achieving 100% train accuracy with a large accuracy gap and lower CV performance.

Well-Generalized Models: Random Forest and AdaBoost maintained high train accuracy (~100%) but small accuracy gaps (<0.05) and strong CV performance, demonstrating the effectiveness of ensemble methods against overfitting.

### KNN Performance

Increasing K reduced sensitivity to noise and slightly improved stability.

In this dataset, all tested K values showed stable performance with minimal differences.

### Impact of Feature Normalization

KNN: Strongly benefits from normalization, improving accuracy and stability.

Decision Tree & Random Forest: Performance largely unaffected by normalization.

AdaBoost: Minimal effect.

### Summary:
Normalization improves overall model quality and reduces performance discrepancies, while ensemble methods like Random Forest and AdaBoost effectively mitigate overfitting.
