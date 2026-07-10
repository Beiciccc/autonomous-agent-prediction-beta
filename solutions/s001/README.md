# s001 — Robust Tabular Portfolio

Released source corresponding to Kaggle submission `54533337`, submitted on 2026-07-10 at 16:07:13 UTC and completed with public score **0.822**.

- Public Kaggle Code: [Robust Tabular Portfolio Submission](https://www.kaggle.com/code/beicicc/robust-tabular-portfolio-submission)
- Scored upload SHA-256: `fd8d03512b2b962c83afaf2014a040508daa80151a8fd6602379b06233434dce`
- Source manifest: [`SHA256SUMS`](SHA256SUMS)
- Aggregate validation data: [`results/s001_meta_validation_summary.csv`](../../results/s001_meta_validation_summary.csv)

## Configuration

The root `SequentialAgent` runs three stages:

1. create and submit a fast CatBoost baseline, with a prior-probability fallback;
2. cross-validate CatBoost, LightGBM, ExtraTrees, and regularized logistic regression, then submit the strongest single-model and rank-blend candidates;
3. select up to two successful internal submissions using returned public scores.

Skill scripts locate persistent inputs and outputs under `/work`, preserve the sample-submission schema, exclude solution-like files from discovery, and sanitize probabilities before writing CSV files.

## Validation evidence

- Current official validator: dry compilation passed for both the source tree and the extracted scored package.
- Sixteen visible tasks: zero model errors.
- Simulated public-selection/private-evaluation mean AUC: `0.80369`.
- Simulated lower-quartile Private AUC: `0.75801`.

These development statistics are aggregate validation results, not hidden leaderboard estimates.

## Dependencies and license

The released scripts use NumPy, pandas, scikit-learn, CatBoost, and LightGBM supplied by the competition runtime. No third-party source is vendored here. Original code in this directory is licensed under the repository's [MIT License](../../LICENSE); competition data and organizer-supplied components remain governed by the Kaggle competition rules.
