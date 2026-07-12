# s003 — Adaptive Small-Sample Portfolio

Released source corresponding to Kaggle submission `54594314`, submitted on 2026-07-12 at 04:06:48 UTC and completed with public score **0.820**.

- Public Kaggle Code: [Adaptive Small-Sample Portfolio Submission](https://www.kaggle.com/code/beicicc/adaptive-small-sample-portfolio-submission)
- Scored upload SHA-256: `f55aa1033cab7073998b84e42b7c93848f179ae63dfe3f681812970d128b0de8`
- Source manifest: [`SHA256SUMS`](SHA256SUMS)
- Aggregate validation data: [`results/s003_meta_validation_summary.csv`](../../results/s003_meta_validation_summary.csv)

## Changes from s002

- The established quick baseline, five-fold model families, OOF-gated rank blends, and final public-score selection are retained.
- For training sets below 1,500 rows, the main CatBoost prediction averages three deterministic cross-validation repeats.
- For training sets up to 2,500 rows, shallow and deep CatBoost variants are compared using training-only OOF AUC.
- The stronger variant is added as one standalone candidate. It is deliberately excluded from the core rank blends.

## Validation evidence

- The official validator compiled both the source tree and the extracted scored package.
- Sixteen visible tasks completed with zero model errors.
- Simulated public-selection/private-evaluation mean AUC: `0.80532` (`+0.00124` versus s002).
- Simulated lower-quartile Private AUC: `0.75812`; minimum Private AUC: `0.65810`.
- Paired task result versus s002: 5 wins, 11 ties, and 0 losses.
- Maximum observed portfolio runtime: `164.0` seconds.

The public score declined from the existing best `0.822` to `0.820`. The visible validation gain was also concentrated: train_13 contributed about 74.7% of the positive paired gain. This result is retained as a diagnostic release, not as the recommended configuration.

Future small-sample experiments should be evaluated on a predeclared task-level confirmation split and rejected when one visible task contributes most of the aggregate gain.

## Dependencies and license

The released scripts use NumPy, pandas, scikit-learn, CatBoost, and LightGBM supplied by the competition runtime. No third-party source is vendored here. Original code in this directory is licensed under the repository's [MIT License](../../LICENSE); competition data and organizer-supplied components remain governed by the Kaggle competition rules.
