# Autonomous Agent Prediction (Beta)

Public experiment record for Kaggle's [Autonomous Agent Prediction (Beta)](https://www.kaggle.com/competitions/autonomous-agent-prediction-beta/overview) competition.

The competition is a meta-learning challenge built from synthetic binary-classification datasets. A submitted configuration is evaluated on its ability to inspect a previously unseen dataset, train models within the evaluation limits, and select predictions that generalize well. Performance is measured with ROC AUC.

This repository contains:

- concise competition and dataset notes;
- reproducible experiment summaries;
- public leaderboard score history;
- cleaned source/configuration snapshots for results selected for public release.

## Current status

The initial scored configuration, [`s001`](solutions/s001), completed as Kaggle submission `54533337` with public score **0.822**. The matching source is also available as a public [Kaggle Code notebook](https://www.kaggle.com/code/beicicc/robust-tabular-portfolio-submission).

## Repository layout

- `docs/competition_notes.md` — public rules, metric, and task summary.
- `data/README.md` — data provenance and redistribution boundary.
- `experiments/experiment_log.md` — chronological experiment ledger.
- `results/public_scores.csv` — public leaderboard observations.
- `results/s001_meta_validation_summary.csv` — aggregate validation statistics across the sixteen visible tasks.
- `solutions/` — cleaned configurations released with scored experiments.

Raw competition files and generated submission archives are not redistributed here. They are available from the official Kaggle competition page subject to its rules.

Original source code in this repository is released under the [MIT License](LICENSE). Competition data and organizer-supplied materials are excluded.
