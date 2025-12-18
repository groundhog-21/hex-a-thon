# Explainable Survival: From Prediction to Trust in Hex

## Inspiration

The Titanic dataset is one of the most well-known machine learning benchmarks. After extensive experimentation and achieving a top-quartile Kaggle score, I realized that improving accuracy was not the hardest part of the problem — **understanding and trusting the model’s decisions was**.

In real-world settings, machine learning models are rarely judged on metrics alone. Stakeholders need to know *why* a prediction was made, *where* the model fails, and *whether* its outputs can be trusted. This project was inspired by that gap between Kaggle-style optimization and decision-ready machine learning.

---

## What I Built

This project is an **end-to-end, explainable machine learning application**, built entirely in Hex.

Rather than focusing on leaderboard performance, it reframes Titanic survival prediction as a **trust and interpretability problem**, delivered through an interactive app with three layers:

- **Interactive prediction**  
  Explore survival probabilities for hypothetical passengers through “what-if” analysis.

- **Local explainability**  
  Understand *why* a specific prediction was made by surfacing the strongest positive and negative drivers.

- **Global model evaluation**  
  Examine where the model performs well — and where it struggles — across demographic and socioeconomic groups.

Together, these views turn a familiar dataset into a **decision-support style experience**, not a competition notebook.

---

## How It Was Built

Several common tabular models were evaluated, including logistic regression and gradient-boosted approaches. A **Random Forest trained with cross-validation** provided the best balance of performance, stability, and interpretability, achieving a public leaderboard score of approximately **0.78**.

To make the model’s reasoning transparent, I integrated **SHAP (SHapley Additive exPlanations)** to support both:

- **Local explanations** (for individual predictions)
- **Global insights** (feature importance and cohort-level error patterns)

Hex made it possible to unify data preparation, modeling, explainability, and interaction in a single workflow — and to expose the results through a polished, shareable app.

---

## Challenges & Learnings

- High-performing models are not necessarily *useful* models unless their behavior is transparent.
- Explainability is most effective when paired with interactive exploration.
- Hex excels at turning raw analysis into a **clear, decision-ready experience**.

---

## Why This Matters

The Titanic dataset is merely a vehicle. The real focus of this project is how modern analytics platforms like Hex can help data scientists build **machine learning systems that people can actually understand and trust**.
