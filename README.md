# Personalized-Healthcare-Recommendation-System-for-ICU-Patients

## Project Overview
Intensive Care Units (ICUs) are critical healthcare environments where patients with severe
or life-threatening conditions receive specialized care. ICU patients often have complex
medical histories and require highly personalized treatment plans. However, the vast amount
of data generated in ICUs—ranging from structured data like lab results and vitals to
unstructured data like clinical notes—poses a significant challenge for healthcare providers.
Analyzing this data manually is time-consuming and error-prone, often leading to delayed or
suboptimal treatment decisions.
To address this challenge, we propose a Personalized Healthcare Recommendation System
for ICU Patients. This system leverages the MIMIC-III dataset, a comprehensive
collection of de-identified ICU patient records.
By combining machine learning, natural language processing (NLP),
 the system aims to:
1. Predict patient Admission by analyzing vital signs, lab results, and medical
history.
2. Predict Length of Stay if patient is admitted.
3. Classify patients into risk levels (low, medium, high) to prioritize critical cases and
optimize resource allocation.
4. Extract insights from clinical notes using advanced NLP techniques to uncover
hidden patterns and improve decision-making.

The ultimate goal of this project is to assist healthcare providers in making informed, timely,
and personalized treatment decisions, ultimately improving patient outcomes and reducing
the burden on ICU resources
Dataset Link: https://www.kaggle.com/datasets/bilal1907/mimic-iii-10k/data


##  Objectives
- Predict ICU Admission Status using vital signs, lab results, and demographic features.
- Predict Length of Stay (LOS) for admitted patients using regression models.
- Clean and preprocess raw clinical notes
- Use TF-IDF to convert notes into numerical features
- Train multiple models to classify risk
- Evaluate the model's performance with metrics like Accuracy, F1 Score, and ROC-AUC

---

##  Dataset
- **Source**: MIMIC-III (NOTEEVENTS.csv, ADMISSIONS.csv)
- **Target Variable**: `HOSPITAL_EXPIRE_FLAG`
- **Number of Categories**: 2 → `0` (Survived), `1` (Expired)

---

##  Models Tested
| Model               | Accuracy | Precision | Recall | F1 Score | AUC-ROC |
|--------------------|----------|-----------|--------|----------|---------|
| Logistic Regression| 76.2%    | 0.71      | 0.68   | 0.69     | 0.74    |
| Random Forest      | 82.5%    | 0.79      | 0.77   | 0.78     | 0.84    |
| XGBoost            | 85.3%    | 0.82      | 0.80   | 0.81     | 0.87    |

>  **Best Model: XGBoost** — It achieved the highest accuracy and AUC-ROC. 

---

## Why Did XGBoost Perform Best?
- Uses **gradient boosting** to reduce model error sequentially
- Incorporates **L1/L2 regularization** to reduce overfitting
- Handles **imbalanced datasets** better using `scale_pos_weight`
- Efficient for high-dimensional, sparse clinical data

---

##  Key Insights
- Text preprocessing (cleaning, TF-IDF) is crucial for working with clinical data
- Logistic Regression is interpretable but limited in complexity
- Ensemble models like XGBoost better capture patient mortality risk patterns

---
