# Explainable Survival: From Prediction to Trust in Hex

👉 **Public Hex App:** https://app.hex.tech/virtual-hackathon/app/031rWcGGGHC7gjaILdmufL/latest  
👉 **Demo Video (v1 narrative):** https://youtu.be/8-Rj1B9vYfc

This repository contains the **modeling, evaluation, and reproducibility artifacts**
supporting a Hex-a-thon project focused on **explainable and trustworthy machine learning**.

The primary deliverable is an interactive ML application built and published in **Hex**.
This repository serves as the **canonical, reproducible source** for the model,
evaluation data, and diagnostics used by the app.

---

## Project Overview

This project reframes the classic Titanic survival prediction problem as a **trust,
error analysis, and interpretability challenge**, rather than a leaderboard optimization task.

The Hex app guides users through three layers:

1. **Survival Prediction** — interactive inference for a hypothetical passenger  
2. **Prediction Drivers** — local explanations showing *why* the model predicts survival or death  
3. **Error Patterns** — global evaluation revealing *where* the model struggles and why  

A key design principle is that **evaluation is data-driven and externalized**:
model behavior is exposed via reusable evaluation datasets rather than hard-coded logic.

---

## What makes Version 2 different

Version 2 introduces a **universal evaluation dataset**, generated offline using
out-of-fold (OOF) predictions, and uploaded to Hex.

This enables:
- Fast app performance (no heavy recomputation at runtime)
- Rich, open-ended analysis via **Hex Threads**
- Reproducible global diagnostics (error rates, cohort analysis, uncertainty, SHAP-based insights)

Threads can now answer questions like:
- *Which passenger groups does the model struggle with most?*
- *Where is the model confidently wrong?*
- *Which features drive disagreement or uncertainty across groups?*

without changing the inference code.

---

## Repository contents

This repository intentionally includes **model and evaluation artifacts** to support
reproducibility of the Hex app.

### What this repository is

- Local experimentation, modeling, and validation in Python
- Feature engineering and model selection using cross-validation
- Offline evaluation using **out-of-fold predictions**
- Canonical artifacts used by the Hex app and Threads

### What this repository is not

- This is not the deployed application itself
- The interactive UI, charts, and AI-powered Threads live in Hex

---

## Key artifacts (committed intentionally)
```
artifacts/
├── model.joblib # Final RandomForest model
├── scaler.joblib # Feature scaler
├── feature_names.json # Model feature contract
├── metrics.json # Offline OOF accuracy and evaluation metadata
├── evaluation_universe.csv # OOF predictions + features + ground truth
├── prediction_error_rates.csv # Error rates by cohort
└── ground_truth_by_cohort.csv # Ground truth survival rates by cohort
```

These artifacts ensure that:
- All reported metrics are verifiable
- Threads operate over a transparent, inspectable evaluation dataset

---

## Tech Stack

- Python 3.11
- pandas, NumPy
- scikit-learn
- SHAP (offline explainability)
- Jupyter
- Hex (notebooks, apps, Threads)

---

## Repository Structure
```
hex-a-thon/
├── notebooks/ # Modeling, validation, evaluation, exports
├── artifacts/ # Models and evaluation datasets (committed)
├── submissions/ # Kaggle submission artifacts
├── requirements.txt
└── README.md
```

---

## Notes

- Model performance is reported using **out-of-fold cross-validation**, not a single holdout split.
- Metrics shown in the app are **offline evaluation results**, provided for context and trust.
- The app prioritizes interpretability, error awareness, and user understanding over optimization.