 # Galen AI
**TEKNOFEST 2026 — Sağlıkta Yapay Zeka Yarışması | Üniversite ve Üzeri**

## Project Overview
Galen AI is a machine learning pipeline developed for the classification of missense 
genetic variants as **Pathogenic** or **Benign**. The project was built using ClinVar 
open-access data as preparation for the TEKNOFEST 2026 Health AI Competition.

The pipeline trains four independent LightGBM models — one general model and three 
disease-specific panel models — and provides SHAP-based explainability for each.

## Team
| Member | Role |
|---|---|
| Javid Rahimli | Data Analysis & Machine Learning |
| Zarifa Salmanova | UI/UX & Visual Design |

## Models & Results
| Panel | ROC-AUC | PR-AUC | F1 | Sensitivity |
|---|---|---|---|---|
| General | 0.9419 | 0.9581 | 0.8826 | 0.8672 |
| Hereditary Cancer | 0.9135 | 0.9405 | 0.8340 | 0.7698 |
| CFTR | 0.9374 | 0.9927 | 0.9726 | 0.9830 |
| PAH | 0.8479 | 0.9884 | 0.9692 | 0.9665 |

## Key Features
- **Anonymous pipeline**: Model trained with anonymized column names (f0–f8) 
  to comply with competition constraints
- **SHAP explainability**: Feature group
