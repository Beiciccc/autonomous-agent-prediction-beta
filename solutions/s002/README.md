# s002 — Five-Fold Weighted Portfolio

Released source corresponding to Kaggle submission `54571974`, submitted on 2026-07-11 at 12:48:44 UTC and completed with public score **0.822**.

- Public Kaggle Code: [Five-Fold Weighted Portfolio Submission](https://www.kaggle.com/code/beicicc/five-fold-weighted-portfolio-submission)
- Scored upload SHA-256: `1f4495d72d5107a4a1b0c63306eb880476aaa93ca67a1af45190b8ab11ff8f0e`
- Source manifest: [`SHA256SUMS`](SHA256SUMS)
- Aggregate validation data: [`results/s002_meta_validation_summary.csv`](../../results/s002_meta_validation_summary.csv)

## Changes from s001

- All candidate models use five stratified folds when class counts permit.
- LightGBM receives encoded categorical columns as native categorical features.
- The candidate set adds an equal-rank top-three blend.
- A top-two weighted blend is emitted only when a coarse OOF grid improves on both the equal blend and strongest single model by at least `0.0005` AUC.
- The weighted gate fired on four of the sixteen visible validation tasks.
- Up to eight manifest-listed portfolio files can be scored internally, preserving the original model coverage before the final public-score selection.

## Validation evidence

- Current official validator: dry compilation passed for both the source tree and extracted package.
- Sixteen visible tasks: zero model errors.
- Simulated public-selection/private-evaluation mean AUC: `0.80409` (`+0.00039` versus s001).
- Simulated lower-quartile Private AUC: `0.75812` (`+0.00011` versus s001).
- Maximum observed portfolio runtime: `143.8` seconds.

The improvement was small and not universal across tasks. On the public leaderboard, s002 matched s001 rather than exceeding it.

## Dependencies and license

The released scripts use NumPy, pandas, scikit-learn, CatBoost, and LightGBM supplied by the competition runtime. No third-party source is vendored here. Original code in this directory is licensed under the repository's [MIT License](../../LICENSE); competition data and organizer-supplied components remain governed by the Kaggle competition rules.
