---
title: "Flight Cancellation Predictor"
description: "A machine-learning web app that predicts flight cancellations using six different classifiers (Naive Bayes, KNN, Logistic Regression, Decision Tree, MLP, Random Forest), with batch evaluation and a real-time inference UI."
tech_stack:
  - "Python"
  - "FastAPI"
weight: 60
---

<div>

End-to-end data-science project from the **Data Science** course at IST. The goal: turn raw flight data into actionable predictions, the right way — with a real preprocessing pipeline, multiple model options, and a serving layer.

## What I built

### Preprocessing pipeline

A reusable transformation pipeline applied identically at training and inference time:

1. **Missing-value imputation**: mean for numeric, mode for categorical.
2. **Type enforcement**: numeric coercion, type standardization.
3. **Cyclic encoding**: sine/cosine transforms for temporal features (Month, DayOfWeek, Quarter, Time blocks) so the model sees Sunday→Monday as adjacent rather than 6→0.
4. **Ordinal encoding** for categorical features.
5. **MinMax scaling** to `[0, 1]`.
6. **Feature selection** down to 37 retained features.

A JSON manifest (`prediction_objects.json`) keeps the pipeline reproducible and the inference path consistent with training.

### Six classifiers, side-by-side

| Algorithm | Library | Use case |
|---|---|---|
| Naive Bayes (Gaussian) | scikit-learn | Baseline, fast |
| K-Nearest Neighbors | scikit-learn | Non-parametric reference |
| Logistic Regression | scikit-learn | Linear baseline |
| Decision Tree | scikit-learn | Interpretable |
| Multi-Layer Perceptron | scikit-learn | Non-linear |
| Random Forest | scikit-learn | Best overall trade-off |

A focus on **imbalanced-class scenarios** (cancellations are rare) shaped the metrics and the resampling strategy.

### Serving layer

A **FastAPI** web app with two endpoints:

- `POST /predict` — single flight, instant prediction.
- `POST /evaluate` — upload a CSV, get accuracy / precision / recall / F1 across all six models.

A vanilla HTML/CSS/JS frontend wraps the endpoints with a usable UI, and `joblib`-persisted models keep the server cold-start cheap.

### Companion work: time series

In parallel I worked on **traffic-volume forecasting** on high-frequency time series, comparing classical statistics (**ARIMA**) with deep learning (**LSTM**) — explored as a separate experiment but on the same data-science core.

</div>
