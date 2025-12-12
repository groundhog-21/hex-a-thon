
# Explainable Survival: From Prediction to Trust in Hex

## Inspiration

The Titanic dataset is one of the most well-known machine learning benchmarks. After spending several months iterating on models and achieving a top-quartile leaderboard score on Kaggle, I realized that the hardest part of the challenge was not improving accuracy—it was **understanding and trusting the model’s decisions**.

In real-world settings, machine learning models are rarely judged solely by performance metrics. Stakeholders want to know *why* a model makes a prediction, *where* it fails, and *whether* its outputs can be trusted. This project was inspired by that gap between Kaggle-style optimization and production-grade, decision-oriented machine learning.

Hex provided an ideal environment to explore this question end-to-end.

---

## What I Built

This project is an **end-to-end, explainable machine learning application** built entirely in Hex. It transforms the classic Titanic survival prediction task into an interactive experience focused on transparency, exploration, and trust.

The project consists of three tightly integrated layers:

1. **A reproducible ML pipeline**
   - Data cleaning and feature engineering
   - Model selection and hyperparameter tuning using cross-validation
   - Final training using a `RandomForestClassifier`

2. **Explainability and diagnostics**
   - Global feature importance to understand overall model behavior
   - Local explanations (per passenger) using SHAP values
   - Cohort-level analysis to identify systematic errors and biases

3. **An interactive Hex app and AI-powered exploration**
   - A prediction interface for “what-if” analysis
   - Visual explanations showing why a prediction was made
   - A Hex Thread that allows users to ask natural-language questions about the model and its behavior

Rather than optimizing for leaderboard score, the goal was to build something that feels closer to a **decision-support product** than a competition notebook.

---

## How It Was Built

### Modeling Approach

I evaluated several common models for tabular classification, including Logistic Regression, Gradient Boosting, XGBoost, LightGBM, and CatBoost. While some boosted models achieved comparable performance, a **Random Forest with `GridSearchCV`** offered the best balance of performance, stability, and interpretability.

The final model achieves a public leaderboard score of approximately **0.78**, placing it comfortably in the top quartile.

### Explainability with SHAP

To move beyond feature importance heuristics, I integrated **SHAP (SHapley Additive exPlanations)**:

- For a given prediction, SHAP decomposes the output as:

\[
f(x) = E[f(X)] + \sum_{i=1}^{n} \phi_i
\]

where \(\phi_i\) represents the contribution of feature \(i\).

This allows both **global reasoning** (which features matter most overall) and **local reasoning** (why this passenger survived or not).

### Hex as the Platform

Hex made it possible to:
- Combine SQL, Python, and visualizations in a single workflow
- Turn analysis into a shareable, interactive application
- Layer AI-driven exploration (Threads) on top of a curated semantic model

The result is something that would be difficult to reproduce with a traditional notebook or BI tool alone.

---

## Challenges Faced

- **Avoiding “yet another Titanic notebook”**  
  The biggest challenge was reframing a well-worn dataset into a meaningful product demonstration rather than a Kaggle exercise.

- **Learning SHAP just deeply enough**  
  SHAP is powerful but complex. The challenge was focusing on explanations that add insight rather than visual noise.

- **Balancing rigor and usability**  
  Accuracy metrics matter, but usability, interpretability, and storytelling matter just as much for real users.

---

## What I Learned

- High-performing models are not necessarily *useful* models unless their behavior is transparent.
- Explainability tools are most valuable when paired with interactive exploration.
- Hex excels as a platform for moving from raw data to a polished, decision-ready experience.

---

## Why This Matters

This project demonstrates how classic machine learning problems can be reframed to emphasize **trust, interpretability, and interaction**—qualities that are essential in real-world deployments.

The Titanic dataset is merely a vehicle. The real subject is how Hex enables analysts and data scientists to build ML systems that people can actually understand and use.
