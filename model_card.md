# 🩺 model_card.md

## 📌 Model Overview

**Model Name:** MIMIC-CDS Risk Model  
**Domain:** Critical Care / ICU Admission Risk  
**Model Type:** Random Forest Classifier  
**Version:** v1.0  
**Status:** Internal Research / Not for Clinical Use  

This model is part of the `mimiccds` framework — a modular Clinical Decision Support (CDS) pipeline trained on real, de-identified MIMIC-IV ICU data. The model predicts the likelihood of ICU admission based on patient-level features available at or near the time of hospital admission.

---

## 📊 Intended Use

- Support exploratory research into interpretable, modular CDS systems  
- Provide a reference implementation for fairness auditing, interpretability, and transparent reporting in healthcare ML
- Not intended for real-time clinical decision-making or deployment without further validation

---

## 📁 Dataset Information

- **Source:** MIMIC-IV (v2.2), publicly available ICU dataset curated by MIT-LCP  
- **Data Used:** `patients.csv`, `admissions.csv`, `diagnoses_icd.csv`  
- **Preprocessing:** Merged by `subject_id`, encoded categorical variables, removed direct identifiers  
- **Label:** Binary ICU admission risk (`y_true`), derived from encounter metadata

---

## 🧠 Model Details

- **Architecture:** RandomForestClassifier from `sklearn.ensemble`
- **Hyperparameters:**
  - `n_estimators=100`
  - `max_depth=10`
  - `class_weight='balanced'`
- **Training/Test Split:** 70% train / 30% test, stratified by label
- **Feature Engineering:** One-hot encoding of categorical features; no imputation needed due to filtered MIMIC subset

---

## 📈 Performance Metrics

| Metric       | Value   |
|--------------|---------|
| Accuracy     | *[insert]* |
| ROC-AUC      | *[insert]* |
| Precision    | *[insert]* |
| Recall       | *[insert]* |
| F1-Score     | *[insert]* |

> Update this table after running metrics in `2_risk_model_training.ipynb`.  
> Replace *[insert]* with output from: `roc_auc_score`, `precision_score`, `recall_score`, `f1_score`.

---

## 🧮 Explainability Approach

- **Primary Method:** Permutation Importance (`sklearn.inspection`)
  - Identified top 15 most influential features
  - Results saved in `permutation_importance.csv`
  - Visualized as bar plot: `permutation_importance_top15.png`
- **Why not SHAP?**
  - SHAP was evaluated but repeatedly failed due to internal matrix shape mismatches
  - Documented failure in `4_model_explainability.ipynb`
  - Switched to model-agnostic, stable permutation method

---

## ⚖️ Fairness Evaluation

- **Demographic Groups Assessed:**
  - Gender (`Male`, `Female`)
  - Race (as encoded in MIMIC)
  - Age Bins (`<40`, `40–65`, `65+`)
- **Approach:**
  - Custom `compute_fairness_metrics()` function to evaluate prediction balance across groups
  - Group-wise metrics computed on test set predictions

---

## ⚠️ Limitations

- Not validated prospectively or externally
- No time-series or longitudinal features used
- Uses static demographic + diagnostic data only
- May not generalize beyond MIMIC-IV context or U.S. ICU systems
- Not interpretable at instance-level (e.g., no SHAP explanations per patient)

---

## 🤖 Ethical & Responsible AI Considerations

- All data is de-identified and used under the MIMIC-IV data use agreement
- Interpretability prioritized via permutation methods and fairness breakdowns
- No personally identifiable information used or retained
- Documentation of failed SHAP attempt included to maintain transparency

---

## 📦 Repository Structure

<p align="center">
  <img src="synthetic/assets/repository_str.png" alt="MIMIC-CDS Overview" width="600"/>
</p>

**Rand Sobczak Jr**  
Emerging Data Scientist • MedTech-Focused | GenAI • ML • Statistics | Raw Data→Action  
Python • SQL • Databricks • Azure • ETL • Tableau | Eagle Scout  
Specializing in AI for Healthcare, Health Informatics, and Explainable ML

---

## 🔗 References

- Johnson et al., “MIMIC-IV: A freely accessible critical care database,” *Scientific Data*, 2020.  
- Breiman, L. “Random Forests,” *Machine Learning*, 2001.  
- Molnar, C. *Interpretable Machine Learning*, 2nd ed.  

---



