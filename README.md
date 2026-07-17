# Autonomous Agent Prediction (Beta)

Public experiment record for Kaggle's [Autonomous Agent Prediction (Beta)](https://www.kaggle.com/competitions/autonomous-agent-prediction-beta/overview) competition.

The competition is a meta-learning challenge built from synthetic binary-classification datasets. A submitted configuration is evaluated on its ability to inspect a previously unseen dataset, train models within the evaluation limits, and select predictions that generalize well. Performance is measured with ROC AUC.

This repository contains:

- concise competition and dataset notes;
- reproducible experiment summaries;
- public leaderboard score history;
- public Kaggle Code references for completed scored experiments.

## Current status

The latest completed experiment, `s008`, reached **0.822** as Kaggle submission `54791549`. It was a byte-identical package replication of `s002` and matched the retained public best at the leaderboard's displayed three-decimal precision. The `s003` and `s004` experiments each completed at **0.820** and remain diagnostic results. All eight scored experiments have corresponding public Kaggle Code notebooks.

## Repository layout

- `docs/competition_notes.md` — public rules, metric, and task summary.
- `data/README.md` — data provenance and redistribution boundary.
- `experiments/experiment_log.md` — chronological experiment ledger.
- `results/public_scores.csv` — public leaderboard observations.
- `results/s001_meta_validation_summary.csv` through `results/s004_meta_validation_summary.csv` — aggregate validation statistics across the sixteen visible tasks.
- `solutions/` — public experiment and Kaggle Code index.

Raw competition files and generated submission archives are not redistributed here. They are available from the official Kaggle competition page subject to its rules.

Original source code in this repository is released under the [MIT License](LICENSE). Competition data and organizer-supplied materials are excluded.
