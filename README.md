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

## Results & Validation

### Random Split Performance
Using a standard random train/test split, the QSAR model achieved:

- **R² ≈ 0.86**
- **RMSE ≈ 0.81**

This performance reflects interpolation within known chemical space, where
structurally similar molecules appear in both training and test sets.

### Scaffold Split Performance (Chem-Aware Validation)
To assess true generalization, a Murcko scaffold split was applied, ensuring
that core molecular scaffolds in the test set were absent from training.

- **Scaffold split R² is lower than random split**
- This decrease is expected and scientifically meaningful

The scaffold split provides a more realistic estimate of model performance on
novel chemotypes, reducing analogue bias and data leakage.

### Interpretation
The observed drop in performance under scaffold splitting indicates that
aqueous solubility is driven by both global physicochemical properties and
scaffold-specific effects. The model generalizes reasonably to unseen
chemistry, consistent with published QSAR benchmarks.

---

## Project Structure

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
