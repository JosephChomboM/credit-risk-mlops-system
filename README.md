# Credict Risk MLOps System

End-to-end **credict default prediction** system built on a real world dataset to show how to go from raw banking style data to a deployed, monitored ML model that could fit into a production enviroment.

---

## 1. Business Problem
Banks need to decide **who is likely to default** on their credit obligations.

This project answers a concrete question:

> "Given a customer's past behavior and financial attribute, what is the probability that they will default in the next period?"

## 2. Dataset

Current dataset:

- **Source**: “Default of Credit Card Clients Dataset” (Kaggle, originally from UCI repository).
- **Task**: Predict whether a client will **default on their credit card** in the next month.
- **Type**: Binary classification.
- **Rows / columns**: ~30k rows, 23+ features (demographics, bill statements, payments).

---

## 3. Technical Goals

This repository is designed to demonstrate:

1. **Solid ML foundations**  
   - Train/test splits, cross-validation  
   - Baseline models (logistic regression, tree-based models)  
   - Proper metrics: ROC AUC, PR AUC, calibration, confusion matrix

2. **Reproducible experimentation**  
   - Config-driven training (YAML)  
   - Scripted pipelines instead of ad-hoc notebooks  
   - Experiment tracking (MLflow or similar)

3. **MLOps best practices (solo-dev scale)**  
   - Clear `src/` structure  
   - Separation of data, features, models, configs  
   - Basic CI (lint, tests, training sanity check)  
   - Packaging (CLI entry points or simple module)

4. **Deployable model**  
   - Simple **FastAPI** service exposing `/predict`  
   - Dockerfile to containerize the service  
   - Example `docker run` / `docker-compose` usage

5. **Monitoring & drift basics**  
   - Log predictions and inputs  
   - Simple drift / data-quality checks  
   - Basic dashboards / reports (even offline, via notebook or script)

- **Phase 1 (Dec 14 – Dec 31)**  
  - Define business problem and success metrics  
  - Download and document dataset (see [Issue #1](https://github.com/JosephChomboM/credit-risk-mlops-system/issues/1))  
  - Build EDA notebook (see [Issue #2](https://github.com/JosephChomboM/credit-risk-mlops-system/issues/2))  
  - Implement config-driven baseline training script (see [Issue #3](https://github.com/JosephChomboM/credit-risk-mlops-system/issues/3))  
  - Make training reproducible via configs and scripts
