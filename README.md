# Solubility Prediction (QSAR)
# QSAR Solubility Prediction (ESOL Dataset)

## Overview
This project implements a Quantitative Structure–Activity Relationship (QSAR) model to predict
aqueous solubility (LogS) of organic molecules using cheminformatics and machine learning.

The workflow covers the full pipeline:
- Molecular representation from SMILES
- Descriptor-based feature engineering
- Model training, validation, and tuning
- Scientific interpretation and visualization

This project is intended as a **research-grade, portfolio-ready example** of applied
cheminformatics and data science.

---

## Dataset
- **ESOL (Delaney) dataset**
- ~1,100 small organic molecules
- Target: measured log solubility in mol/L

---

## Methodology
- **Descriptors**: Molecular weight, LogP, TPSA, hydrogen bond counts, rings, rotatable bonds
- **Model**: Random Forest Regressor
- **Validation**: Train/test split + 5-fold cross-validation
- **Metrics**: R² and RMSE

---

## Results
- The model captures key physicochemical drivers of solubility:
  - Lipophilicity (LogP)
  - Molecular size
  - Polarity (TPSA)
- Performance is consistent with published baseline QSAR models.

A parity plot comparing observed vs predicted LogS is provided in `reports/figures/`.

---

## Project Structure

---

solubility-prediction/
├── data/ # ESOL dataset
├── notebooks/ # QSAR analysis notebook
├── models/ # Trained model
├── reports/
│ ├── metrics.json # Model performance
│ └── figures/ # Parity plot

---

## Tools & Technologies
- Python
- RDKit
- pandas, scikit-learn
- Jupyter Notebook
- Git & GitHub

---

## Author
**Theresia Cate**  
Dr. rer. nat.
