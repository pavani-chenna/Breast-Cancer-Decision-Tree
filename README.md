# Breast Cancer Classification using Decision Trees (Wisconsin WBC Dataset)

This project focuses on building, evaluating, and visualizing a **Decision Tree Classifier** to predict breast cancer diagnosis (Malignant or Benign) using the **Wisconsin Breast Cancer (WBC) dataset**. The work includes complete preprocessing, model training, performance evaluation, cross-validation, feature importance analysis, decision-boundary visualization, tree visualization, and prediction on new samples.

---

## 📌 Objective
The primary goal of this project is to identify whether a tumor is **Malignant (1)** or **Benign (0)** based on several diagnostic features computed from breast mass images. A Decision Tree Classifier is used due to its interpretability and suitability for medical decision-making problems.

---

## 📂 Dataset Overview
The dataset used (`wbc.csv`) contains:
- Diagnostic labels (M or B)
- 30 numeric features describing tumor characteristics such as:
  - radius_mean
  - texture_mean
  - perimeter_mean
  - area_mean
  - smoothness, compactness, concavity, symmetry, fractal dimension, etc.
- Extra unnecessary columns such as `id` and `Unnamed: 32`

### ✔ Preprocessing Steps Performed
- Loaded the WBC dataset using pandas  
- Removed irrelevant columns:
  - `id`
  - `Unnamed: 32`
- Checked for missing values (none present after cleanup)
- Dropped duplicate rows
- Converted diagnosis labels into numeric format:
  - Malignant → **1**
  - Benign → **0**
- Defined:
  - **X** = all numeric features  
  - **y** = encoded diagnosis label  
- Performed train-test split (80% training, 20% testing)

---

## 🌳 Model Used: Decision Tree Classifier
The Decision Tree model was chosen because:
- It is easy to interpret  
- It does not require feature scaling  
- It captures non-linear relationships  
- It provides clear visual representation of decision rules  

The model was trained using the cleaned feature set and then evaluated on the test set.

---

## 📊 Model Evaluation
After training, the model was evaluated using:

### **1. Accuracy**
Measures how often the model predicts correctly.

### **2. F1-Score**
Balances precision and recall, especially useful for medical datasets.

Both metrics were calculated on the test dataset.

---

## 🔧 Reducing Overfitting: Cross-Validation
To optimize the model and prevent overfitting:
- Multiple **max_depth** values were tested  
- 10-fold cross-validation was applied  
- Training accuracy and validation accuracy were compared  
- The best-balanced depth was selected  

This ensures the final model generalizes well to unseen data.

---

## 🎨 Visualization & Analysis

### **1. Decision Boundary Visualization**
A decision boundary plot was created using only two features:
- `radius_mean`
- `texture_mean`

This allows visual comparison between:
- Decision Tree Classifier
- Logistic Regression (as a baseline)

The plot shows how each model separates malignant and benign classes.

---

### **2. Feature Importance**
Feature importance values were extracted from the Decision Tree, showing which biological measurements most strongly influence the final prediction.  
This is crucial for:
- Model interpretability  
- Understanding key indicators of breast cancer  
- Supporting medical decision-making  

---

### **3. Decision Tree Visualization**
The entire trained tree was plotted, showing:
- Splitting features
- Threshold values
- Gini impurity
- Class distribution
- Leaf predictions


---

## 🔮 Prediction on New Data
The trained Decision Tree was used to make predictions on a new unseen data sample (manually provided vector).  
The model outputs:
- Predicted class (0 or 1)
- Probability of malignancy / benign

This demonstrates the model’s applicability to real-world diagnostic inputs.

---



