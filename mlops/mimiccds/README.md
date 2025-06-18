
# 🏥 mimiccds
### *Modular CDS Framework for Real ICU Data (MIMIC-IV)*

<p align="center">
  <img src="https://img.shields.io/badge/MIMIC--IV-v2.2-lightgrey" />
  <img src="https://img.shields.io/badge/FHIR-compliant-success" />
  <img src="https://img.shields.io/badge/SHAP-enabled-orange" />
  <img src="https://img.shields.io/badge/GenAI-ClinicalBERT-yellowgreen" />
  <img src="https://img.shields.io/badge/Python-3.10-blue" />
</p>

> 🔄 This repository extends [`smartcds`](https://github.com/sobcza11/smartcds), a synthetic-data prototype for modular CDS pipelines. `mimiccds` demonstrates the same architecture using real de-identified ICU data from MIMIC-IV.

---

## 🧠 Objective

To simulate modular CDS using **real-world ICU data** with a pipeline that spans:
- Cohort selection from MIMIC-IV
- Model-based risk flagging (e.g., sepsis, mortality, readmission)
- SHAP-based explainability of predictions
- ClinicalBERT-based note summarization
- Export to **FHIR-compatible** resources

---

## 📂 Key Modules

| Notebook | Description |
|----------|-------------|
| `1_mimic_data_overview` | MIMIC-IV cohort exploration & filtering |
| `2_risk_model_training` | Model training on clinical outcomes |
| `3_shap_explainer` | SHAP plots for model transparency |
| `4_genai_summary` | Clinical note summarization w/ ClinicalBERT |
| `5_fhir_mapping_export` | Export MIMIC fields to FHIR JSON format |

---

## 🔒 Data Use Compliance

This project uses the **public MIMIC-IV v2.2** dataset from [PhysioNet](https://physionet.org/content/mimiciv/), accessed under credentialed approval. No private health information (PHI) is used.

---

## 📎 License

MIT License — free to use with attribution.

> 🔁 Built as a **real-data extension** of [`smartcds`](https://github.com/sobcza11/smartcds), which demonstrates the same architecture using synthetic inputs.

'
'