# Explainable Survival: From Prediction to Trust in Hex

This repository contains local experimentation, modeling, and explainability work
supporting a Hex-a-thon project focused on **explainable machine learning**.

The primary deliverable is an interactive ML application built and published in **Hex**.
This repo serves as the development and experimentation environment.

---

## Project Overview

The goal of this project is to reframe the classic Titanic survival prediction problem
as a **model trust and interpretability challenge**, rather than a leaderboard optimization task.

Key themes:
- Reproducible ML pipelines
- Model diagnostics and error analysis
- Explainability using SHAP
- Clear separation between experimentation and presentation

---

## Tech Stack

- Python 3.11
- pandas, NumPy
- scikit-learn
- SHAP
- matplotlib, seaborn
- Jupyter
- Hex (notebooks, apps, Threads)

---

## Repository Structure
```
hex-a-thon/
├── data/
│ ├── raw/ # original datasets (not committed)
│ └── processed/ # cleaned / feature-engineered data
├── notebooks/ # EDA, modeling, explainability experiments
├── src/ # reusable modeling and explanation code
├── requirements.txt
└── README.md
```

---

## Notes

- The final user-facing experience lives in Hex.
- This repository is intentionally kept minimal and reproducible.
- Model performance is secondary to interpretability and usability.