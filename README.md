# Employee Retention Predictor  

A machine learning project designed to help organizations **proactively** identify employees at risk of leaving, enabling targeted retention strategies and reducing turnover costs.  

## 📌 Project Overview  
Employee retention is a critical challenge in modern organizations, especially in high-competition industries like software development. Traditional **reactive** approaches such as exit interviews only capture insights after employees have left.  

This project leverages historical HR data and machine learning models to predict the probability of an employee leaving **before** it happens, enabling proactive intervention.  

Our final solution uses a **Random Forest Classifier** that achieved an outstanding **ROC-AUC score of 0.991** on the test dataset.  

---

## 🎯 Objectives  
- Predict the likelihood of an employee leaving using historical HR data.  
- Provide probability-based predictions to assess attrition risk.  
- Maintain interpretability by highlighting key drivers of attrition.  
- Enable HR departments to take **targeted retention actions** proactively.  

---

## 📂 Dataset Description  
The dataset (14,249 rows initially) contains employee information such as:  
- **satisfaction** – Employee satisfaction level (0–1)  
- **last_evaluation** – Most recent performance evaluation score (0–1)  
- **n_projects** – Number of projects handled  
- **avg_monthly_hrs** – Average monthly working hours  
- **tenure** – Years with the company  
- **filed_complaint** – Whether the employee filed a complaint (binary)  
- **recently_promoted** – Whether the employee was promoted in the last 5 years (binary)  
- **department** – Department name  
- **salary** – Categorical (low, medium, high)  
- **status** – Target variable (Left/Employed)  

---

## 🏛️ Architecture  
<img width="414" height="608" alt="image" src="https://github.com/user-attachments/assets/c0a07a76-ae22-4b4a-aa84-394694e50967" />

---

## 🛠 Methodology  

### 1. **Data Preprocessing**
- Removed duplicates and temporary employees.
- Standardized categorical values.
- Imputed missing values and created missing indicators.
- One-hot encoded categorical features.
- Standardized numerical features for certain algorithms.

### 2. **Feature Engineering**
- Created new features:
  - `underperformer`
  - `unhappy`
  - `overachiever`
- One-hot encoded `department` and `salary`.

### 3. **Modeling**
Implemented and tuned multiple models:  
- Logistic Regression  
- Random Forest Classifier ✅ *(Best performing)*  
- XGBoost Classifier  
- K-Nearest Neighbors (KNN)  
- Decision Tree Classifier  
- Support Vector Classifier (SVC)  

**Evaluation Metric:** ROC-AUC (due to class imbalance)  

---

## 📊 Results  
<img width="1235" height="528" alt="image" src="https://github.com/user-attachments/assets/af61b0c0-b058-49dc-8335-ae28c35eaf75" />



**Key Insights from Feature Importance (Random Forest):**
1. **tenure** – Most important predictor.
2. **satisfaction** – Lower satisfaction strongly linked to leaving.
3. **n_projects** – Extreme counts indicate risk.
4. **avg_monthly_hrs** – Both overwork and underwork correlated with attrition.
5. **last_evaluation** – Underperformers and overachievers both have higher risk.

---
