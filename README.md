# Dynamic Machine Learning Models for Predicting Persistent Acute Kidney Injury After Cardiac Surgery Based on Modifiable Perioperative Risk Factors

This repository contains the code of the study:
**"Dynamic machine learning models for predicting persistent acute kidney injury after cardiac surgery based on modifiable perioperative risk factors"**

The repository provides code for biosignal data preprocessing, machine learning model development, performance evaluation, and interpretability analysis used in the manuscript.

---

## 🧩 Installation

This codebase requires Python 3.10.6.

Clone the repository and install dependencies:
```bash
pip install -r requirements.txt
```

---

## 📂 Data Preprocessing

Please refer to **`pAKI_biosignal_preprocessing.ipynb`** for details on:
- Extraction of rSO2 (regional cerebral oxygen saturation) data
- Processing of hemodynamic parameters: MAP (mean arterial pressure), PP (pulse pressure), CVP (central venous pressure), and CI (cardiac index)
- Segmentation of perioperative phases (pre-CPB, intra-CPB, post-CPB)
- Feature engineering including mean, variability (CV, ARV), threshold-based duration, and area under the curve (AUC) calculations

---

## 🧠 Model Development

Machine learning model training and evaluation workflows are implemented in **`pAKI_analysis.ipynb`**.

Key components include:
- **Ensemble model construction** — integration of multiple classifiers including XGBoost, Random Forest, and Extra Trees Classifier
- **Temporal validation strategy** — train/validation split with 1-year prospective test set
- **Patient characteristics analysis** — statistical comparison of baseline and perioperative characteristics between AKI and non-AKI groups

---

## 🔍 Performance Evaluation

Model performance assessment includes:
- **Discrimination metrics** — AUROC and AUPRC for binary classification
- **Classification metrics** — accuracy, sensitivity, specificity, PPV, NPV, and F1-score
- **Bootstrap analysis** — 95% confidence intervals for all performance metrics using bootstrap resampling
- **Net Reclassification Improvement (NRI)** — improvement in risk classification compared to baseline clinical models
- **Clinical outcomes** — adjusted odds ratios (OR) for in-hospital mortality (IHM) 

Performance evaluation code is integrated within **`pAKI_analysis.ipynb`**.

---

## 💡 Model Interpretability Analysis

For explainability and clinical insight generation, the following analyses are provided in **`pAKI_analysis.ipynb`**:

### SHAP Analysis
- **SHAP summary plots** — global feature importance ranking
- **SHAP dependence plots** — visualization of feature-outcome relationships with interaction effects
- Feature importance quantification across different scenarios

### Partial Dependence Plots (PDP)
- Individual feature effect visualization

### Decision Curve Analysis (DCA)
- Clinical utility assessment across different probability thresholds

### Calibration Analysis
- Calibration curve generation
- Agreement between predicted probabilities and observed outcomes

---

## ⚠️ Synthetic Data Notice

Due to patient privacy and data protection regulations, the original patient data cannot be publicly shared. The synthetic dataset provided in this repository was generated for demonstration purposes only by:
1. Taking the `df_combined` dataframe from **`pAKI_analysis.ipynb`**
2. Independently shuffling each column row-by-row
3. Adding random noise to each feature
4. Randomly selecting 100 samples from the shuffled dataset

**Important:** This synthetic data does not represent real patient information and should only be used to understand the code structure and workflow. Results obtained from this synthetic dataset do not reflect the actual findings reported in the manuscript.

---

## 📘 Citation

If you use this code or reproduce results from the study, please cite our paper:
```
to be updated
```

---

