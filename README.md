🫀 Heart Disease Risk Prediction — Ensemble ML (Top 0.7%)
📌 Overview

This repository contains my solution to a heart disease classification competition, where I achieved:

Private Leaderboard Score: 0.88381

Final Rank: 4011 / 4037

Percentile: Top 0.7% (99.3rd percentile)

The solution focuses on probability-calibrated ensemble learning and robust cross-validation to ensure strong generalization performance.

🧠 Problem Statement

Predict the presence of heart disease using structured clinical features.

This is a binary classification task with evaluation based on predictive performance on a hidden test set.

🏗️ Modeling Strategy

Rather than relying on a single model, I built a softmax probability voting ensemble composed of diverse learners:

Logistic Regression

Random Forest Classifier

XGBoost

LightGBM

Gradient Boosting Classifier

The ensemble weights were optimized via cross-validation instead of uniform averaging.

🔬 Why This Approach?

The architecture balances:

Low-variance linear baseline (Logistic Regression)

Bagging stability (Random Forest)

Boosting power (XGBoost, LightGBM, GBC)

Model diversity to reduce correlated error

Probability blending for calibration stability

The result was strong generalization, demonstrated by minimal leaderboard shift between public and private splits.

📊 Validation Strategy

Stratified cross-validation

No leaderboard probing for tuning

Ensemble weights optimized using validation performance

Focus on stability rather than public leaderboard gain

Public Rank: 4010
Private Rank: 4011

This near-identical performance suggests strong generalization.

🚀 Key Takeaways

Model diversity improves stability.

Weight-optimized probability ensembles outperform naive averaging.

Cross-validation discipline prevents leaderboard overfitting.

Generalization consistency > leaderboard chasing.

🛠️ Tech Stack

Python

Scikit-learn

XGBoost

LightGBM

NumPy / Pandas

📈 Future Improvements

Explicit probability calibration (Platt scaling / isotonic)

Stacking with meta-learner

SHAP-based interpretability

Threshold optimization for clinical deployment
