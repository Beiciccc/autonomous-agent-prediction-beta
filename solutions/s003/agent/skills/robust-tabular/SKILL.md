---
name: robust-tabular
description: Builds reliable binary-classification probability submissions with a fast CatBoost fallback and a sample-size-adaptive portfolio of stable CatBoost variants, native-categorical LightGBM, ExtraTrees, regularized logistic, and OOF-gated rank blends.
---

# Robust Tabular Portfolio

Use the supplied scripts without editing them.

## `scripts/quick_baseline.py`

Discovers the current train, test, and sample-submission files under `/work`; infers the ID and binary target; writes a prior fallback first; then attempts a fast CatBoost model. It always leaves `/work/quick_baseline.csv` when the sample schema is available.

## `scripts/run_portfolio.py`

Runs five-fold candidate models. For training sets below 1,500 rows it averages three deterministic CatBoost CV repeats. Up to 2,500 rows it also adds one OOF-selected CatBoost diversity candidate. The script writes model, equal-rank, and OOF-gated weighted-rank CSVs under `/work`, and prints one final `PORTFOLIO_MANIFEST` JSON line listing the absolute files in cross-validation order. Submit only paths from that manifest.

Both scripts exclude solution, answer, truth, and ground-truth files from discovery. They preserve the sample-submission columns, order, and row count and clip finite probabilities to `[0, 1]`.
