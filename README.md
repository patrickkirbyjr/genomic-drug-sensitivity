# Precision Oncology: Genomic Drug Sensitivity Prediction

## 📌 Project Overview
This project applies machine learning to precision oncology, specifically aiming to predict cancer drug sensitivity (measured as $\text{pIC}_{50}$) based on two distinct data modalities:
1.  **Genomic Features:** Mutation data from cancer cell lines (GDSC).
2.  **Chemical Structures:** Molecular fingerprints of drugs derived from SMILES strings.

By integrating these features, the model seeks to identify biomarkers and chemical properties that drive drug efficacy, utilizing **scaffold splitting** to ensure the model generalizes well to novel chemical structures.

## 📂 Project Structure
The workflow is divided into four sequential Jupyter notebooks:

| File | Description |
| :--- | :--- |
| **`01_data_preprocessing.ipynb`** | Imports raw genomic and drug data, generates chemical fingerprints using **RDKit**, handles missing values, and merges datasets into a unified format. |
| **`02_exploratory_data_analysis.ipynb`** | Visualizes $\text{IC}_{50}$ distributions, analyzes mutation frequencies, and computes correlation heatmaps between gene mutations and chemical features. |
| **`03_splitting.ipynb`** | Implements **Murcko Scaffold Splitting** to create rigorous train/test sets based on chemical structure (preventing data leakage) and performs feature selection. |
| **`04_modeling.ipynb`** | Trains and evaluates regression models (**Ridge, Random Forest, XGBoost**) using **Optuna** for hyperparameter tuning and **SHAP** for interpretability. |

## 🛠️ Dependencies
To run this project, you will need the following Python libraries. You can install them via pip or conda:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn xgboost optuna shap joblib rdkit pubchempy pyjanitor