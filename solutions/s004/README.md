# s004 — Small-Sample Variance Reduction

Released source corresponding to Kaggle submission `54627211`, submitted on 2026-07-13 at 00:54:51 UTC and completed with public score **0.820**.

- Public Kaggle Code: [Small-Sample Variance Reduction Submission](https://www.kaggle.com/code/beicicc/small-sample-variance-reduction-submission)
- Scored upload SHA-256: `768814ef51bbe4900b3ea2e4eee687fd3359d90d38327c39b879040dc0f5d94b`
- Source manifest: [`SHA256SUMS`](SHA256SUMS)
- Aggregate validation data: [`results/s004_meta_validation_summary.csv`](../../results/s004_meta_validation_summary.csv)

## Changes from s002

- The established quick baseline, five-fold model families, OOF-gated rank blends, and final public-score selection are retained.
- For training sets below 1,500 rows, the main CatBoost prediction averages three deterministic cross-validation repeats.
- The standalone CatBoost variant evaluated in s003 is removed.

## Validation evidence

- The official validator compiled both the source tree and the extracted scored package.
- A task-level design/confirmation split was fixed before candidate selection, and the eight confirmation tasks were evaluated once after the candidate was frozen.
- Design mean delta versus s002: `+0.00026784` with 2 wins, 6 ties, and 0 losses.
- Confirmation mean delta versus s002: `+0.00015597` with 2 wins, 6 ties, and 0 losses.
- Full sixteen-task simulated mean Private AUC: `0.80429809` versus `0.80408619` for s002.
- Full paired result: 4 wins, 12 ties, and 0 losses; lower-quartile AUC remained `0.75811612`, while minimum AUC improved from `0.64331617` to `0.64425842`.
- The largest single-task share of total positive gain was `35.4%`.
- All sixteen tasks completed with zero model errors; maximum observed portfolio runtime was `239.7` seconds.

The public score matched s003 at `0.820` and remained below the retained `0.822` best from s001/s002. Repeated validation of the same highly correlated model family reduced visible-task variance but did not improve the hidden public score. This configuration is retained as a diagnostic release, not as the recommended version.

Future experiments should first add a genuinely lower-correlation prediction source or feature view rather than changing only repeat counts, thresholds, or existing-family blends.

## Dependencies and license

The released scripts use NumPy, pandas, scikit-learn, CatBoost, and LightGBM supplied by the competition runtime. No third-party source is vendored here. Original code in this directory is licensed under the repository's [MIT License](../../LICENSE); competition data and organizer-supplied components remain governed by the Kaggle competition rules.
