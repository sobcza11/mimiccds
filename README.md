<<<<<<< HEAD
<h1 align="center">🏥 MIMIC-CDS</h1>
<h3 align="center"><i>Modular CDS Framework for Real ICU Data (MIMIC-IV)</i></h3>

<p align="center">
  <img src="https://img.shields.io/badge/MIMIC--IV-v2.2-lightgrey" />
  <img src="https://img.shields.io/badge/FHIR-compliant-success" />
  <img src="https://img.shields.io/badge/SHAP-disabled-red" />
  <img src="https://img.shields.io/badge/Explainability-Permutation%20Importance-blueviolet" />
  <img src="https://img.shields.io/badge/Python-3.10-blue" />
  <img src="https://img.shields.io/badge/License-MIT-green.svg" />
</p>

---

## 🧠 Objective

To simulate a **modular Clinical Decision Support (CDS)** pipeline using real-world ICU data via an integrated framework that spans:
- Cohort selection from MIMIC-IV
- Risk prediction using ML models (e.g., sepsis, readmission)
- Transparent reasoning via model interpretability
- (Optional) ClinicalBERT-based summarization of notes
- Export to standardized **FHIR-compatible** formats

This system models how modern CDS platforms can bridge data science and clinical workflows while preserving transparency, modularity, and alignment with **ethical AI** principles.

---

## 📂 Key Modules

| Notebook | Description |
|----------|-------------|
| `1_data_preparation.ipynb` | Cohort creation and merging MIMIC-IV tables |
| `2_risk_model_training.ipynb` | ICU risk model training + prediction export |
| `3_fairness_analysis.ipynb` | Fairness metrics across gender, race, and age |
| `4_model_explainability.ipynb` | Global interpretability using Permutation Importance |
| `5_model_card.ipynb` | Structured model card (see below) for responsible ML reporting |

---

## 📊 Interpretability & Trust

This project foregrounds **explainability and ethical alignment**:
- ❌ **SHAP** was evaluated but excluded due to known incompatibilities with class-weighted ensembles
- ✅ **Permutation Importance** was used as a model-agnostic alternative
- 📈 Fairness metrics computed for race, gender, and age groups

---

## 📤 Data & Ethics

- 📦 **Dataset**: [MIMIC-IV v2.2](https://physionet.org/content/mimiciv/)
- ✅ Fully **de-identified** under the official data use agreement
- 🔒 No PHI stored, transmitted, or processed outside local environment
- ⚖️ Built in line with **Responsible AI** principles:
  - Fairness
  - Transparency
  - Nonmaleficence

---

## 📤 Repository Structure

<p align="center">
  <img src="synthetic/assets/repository_str.png" alt="MIMIC-CDS Overview" width="600"/>
</p>


---

## 🚀 Quickstart

```bash
# Clone the repository
git clone https://github.com/sobcza11/mimiccds.git
cd mimiccds

# (Optional) Create a virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Launch notebooks
jupyter lab

---

## 📚 Citation

If using this project in academic or research work, please cite the MIMIC-IV dataset per [MIT-LCP guidelines](https://mimic.mit.edu/docs/iv/modules/data-reference/).

=======
# mimiccds
>>>>>>> 1c16d4339fe2c84d008b1cab57beb65d5bcc679f
