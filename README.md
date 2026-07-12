# Autonomous Agent Prediction (Beta)

Public experiment record for Kaggle's [Autonomous Agent Prediction (Beta)](https://www.kaggle.com/competitions/autonomous-agent-prediction-beta/overview) competition.

The competition is a meta-learning challenge built from synthetic binary-classification datasets. A submitted configuration is evaluated on its ability to inspect a previously unseen dataset, train models within the evaluation limits, and select predictions that generalize well. Performance is measured with ROC AUC.

This repository contains:

- concise competition and dataset notes;
- reproducible experiment summaries;
- public leaderboard score history;
- cleaned source/configuration snapshots for results selected for public release.

## Current status

The best public score remains **0.822**. [`s001`](solutions/s001) first reached it as submission `54533337`; the five-fold weighted variant [`s002`](solutions/s002) later matched it as submission `54571974`. The sample-size-adaptive [`s003`](solutions/s003) completed at **0.820** and was not adopted as the best configuration. All three releases have corresponding public Kaggle Code notebooks.

## Repository layout

- `docs/competition_notes.md` — public rules, metric, and task summary.
- `data/README.md` — data provenance and redistribution boundary.
- `experiments/experiment_log.md` — chronological experiment ledger.
- `results/public_scores.csv` — public leaderboard observations.
- `results/s001_meta_validation_summary.csv`, `results/s002_meta_validation_summary.csv`, and `results/s003_meta_validation_summary.csv` — aggregate validation statistics across the sixteen visible tasks.
- `solutions/` — cleaned configurations released with scored experiments.

Raw competition files and generated submission archives are not redistributed here. They are available from the official Kaggle competition page subject to its rules.

Original source code in this repository is released under the [MIT License](LICENSE). Competition data and organizer-supplied materials are excluded.
