# Autonomous Agent Prediction (Beta)

Public experiment record for Kaggle's [Autonomous Agent Prediction (Beta)](https://www.kaggle.com/competitions/autonomous-agent-prediction-beta/overview) competition.

The competition is a meta-learning challenge built from synthetic binary-classification datasets. A submitted configuration is evaluated on its ability to inspect a previously unseen dataset, train models within the evaluation limits, and select predictions that generalize well. Performance is measured with ROC AUC.

This repository contains:

- concise competition and dataset notes;
- reproducible experiment summaries;
- public leaderboard score history;
- public Kaggle Code references for completed scored experiments.

## Current status

The latest completed scored run, `s024`, reached **0.822** as Kaggle submission `55173926`. It hardens CSV discovery against forbidden directory paths and files that resolve outside the task root while preserving the established model, sampling, preprocessing, and selection configuration. A targeted synthetic test removed both failure modes; 32/32 discovery and loaded-data comparisons across the sixteen visible tasks were exact. The official result matched the retained public best at the leaderboard's displayed three-decimal precision, so it supports the path-safety repair without establishing a leaderboard improvement. The `s003` and `s004` experiments each completed at **0.820** and remain diagnostic results. All twenty-four scored runs have corresponding public Kaggle Code records.

## Repository layout

- `docs/competition_notes.md` — public rules, metric, and task summary.
- `data/README.md` — data provenance and redistribution boundary.
- `experiments/experiment_log.md` — chronological experiment ledger.
- `results/public_scores.csv` — public leaderboard observations.
- `results/s001_meta_validation_summary.csv` through `results/s004_meta_validation_summary.csv` — aggregate validation statistics across the sixteen visible tasks.
- `solutions/` — public experiment and Kaggle Code index.

Raw competition files and generated submission archives are not redistributed here. They are available from the official Kaggle competition page subject to its rules.

Original source code in this repository is released under the [MIT License](LICENSE). Competition data and organizer-supplied materials are excluded.
