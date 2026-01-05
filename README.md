# Precision Oncology: Genomic Drug Sensitivity Prediction

## 🧬 Project Overview
This project establishes an **in-silico drug screening pipeline** designed to predict the sensitivity of cancer cell lines to various drug compounds. By integrating high-dimensional **genomic mutation profiles** with **chemical structure data (SMILES)**, the model identifies potential therapeutic candidates.

A key focus of this project is **methodological rigor in validation**. Unlike standard random splits, this pipeline employs **Murcko Scaffold Splitting** to prevent data leakage and simulate real-world drug discovery scenarios, ensuring the model generalizes well to structurally distinct chemical series.

## 🚀 Key Features
* **Multi-Modal Data Integration:** Merges genomic mutation data (cell lines) with molecular fingerprints (drugs) derived from raw **SMILES** strings.
* **Robust Validation Strategy:** Implements **Murcko Scaffold Splitting** via RDKit to mimic prospective clinical trials and avoid overfitting to specific chemical families.
* **Feature Engineering:** Utilizes **Morgan Fingerprints (ECFP4)** for chemical representation and PCA for dimensionality reduction.
* **Explainable AI (XAI):** Leverages **SHAP (SHapley Additive exPlanations)** to interpret "black box" predictions and identify key genomic biomarkers driving drug response.
* **Activity Cliff Analysis:** Includes a failure analysis module to detect "Activity Cliffs"—instances where structurally similar molecules exhibit divergent biological efficacy.

## 🛠️ Tech Stack
* **Languages:** Python
* **Bio/Cheminformatics:** RDKit, PubChemPy
* **Machine Learning:** XGBoost, Scikit-Learn, Optuna (Hyperparameter Tuning)
* **Interpretability:** SHAP
* **Data Manipulation:** Pandas, NumPy, Janitor

## 📂 Repository Structure

```text
├── data/                      # Raw and processed datasets (gitignored)
├── models/                    # Serialized models (.joblib)
├── outputs/                   # Generated plots (SHAP summaries, correlation heatmaps)
├── 01_data_preprocessing.ipynb # Data cleaning, SMILES canonicalization, and merging
├── 02_exploratory_data_analysis.ipynb # Global mutation rates & correlation analysis
├── 03_splitting.ipynb         # Murcko Scaffold generation & Train/Test splitting
├── 04_modeling.ipynb          # Model training (Ridge, RF, XGBoost), Evaluation & SHAP
├── README.md                  # Project documentation
└── requirements.txt           # Python dependencies
