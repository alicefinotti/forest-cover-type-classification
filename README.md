# Forest Cover Type Classification

## Overview

Predicting one of seven forest cover types from cartographic and environmental variables using the [Kaggle Forest Cover Type Prediction dataset](https://www.kaggle.com/competitions/forest-cover-type-prediction/data). The labeled dataset contains **15,120 observations**, balanced across the seven classes.

This group project examines how terrain-informed feature engineering, model selection, and ensemble learning improve classification performance.

## Approach

- **Exploratory analysis:** Examine cover-type distributions, soil and wilderness indicators, elevation, hydrology and correlated features.
- **Feature engineering:** Construct hydrology-distance, hillshade, nonlinear terrain and ecological zone variables, with an ablation study to evaluate their contribution.
- **Model comparison:** Benchmark logistic regression and tree-based classifiers using stratified cross-validation.
- **Optimization:** Tune LightGBM, XGBoost and ExtraTrees with Optuna on the development sample, reserving a 20% holdout for evaluation.
- **Ensembling:** Combine tuned class probabilities through soft voting and assess class-level precision, recall and confusion patterns.

## Results

The final **LightGBM + XGBoost + ExtraTrees** ensemble achieved approximately **0.90 accuracy on the labeled holdout** and **0.86 on the Kaggle public leaderboard**, as documented in the [project report](report.pdf). Feature ablation indicated that nonlinear terrain terms and hydrology-derived features provided the largest improvements. The main remaining errors involved forest types with overlapping ecological characteristics, particularly classes 1 and 2.

## Files

- [`forest_cover_classification.ipynb`](forest_cover_classification.ipynb) — Feature engineering, ablation, model comparison, tuning, evaluation and predictions.
- [`eda_visualizations.ipynb`](eda_visualizations.ipynb) — Exploratory figures and dataset diagnostics.
- [`report.pdf`](report.pdf) — Full project methodology, results and analysis.
