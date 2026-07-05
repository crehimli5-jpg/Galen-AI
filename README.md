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
- **SHAP explainability**: Feature group analysis for all 4 panels
- **Threshold optimization**: Systematic sweep from 0.30 to 0.65 for clinical 
  risk scenarios
- **Class imbalance handling**: class_weight='balanced' for PAH and CFTR panels
- **Clinical Stress Test awareness**: Threshold strategy adjusted for 
  Benign-dominant test sets

## Tech Stack
| Library | Version |
|---|---|
| lightgbm | 4.6.0 |
| scikit-learn | 1.6.1 |
| shap | 0.51.0 |
| pandas | 2.2.2 |
| numpy | 2.0.2 |

## How to Run
1. Open `GalenAI.ipynb` in Google Colab
2. Upload `variant_summary.txt.gz` from ClinVar to `/content/`
3. Run all cells sequentially
4. All experiments use `random_state=42` for full reproducibility

## Data
Training data: NCBI ClinVar `variant_summary.txt.gz`  
- 300,000 rows loaded, 170,691 usable variants after filtering  
- Labels: Pathogenic + Likely Pathogenic → 1, Benign + Likely Benign → 0
