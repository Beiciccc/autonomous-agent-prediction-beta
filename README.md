# Autonomous Agent Prediction (Beta)

Public experiment record for Kaggle's [Autonomous Agent Prediction (Beta)](https://www.kaggle.com/competitions/autonomous-agent-prediction-beta/overview) competition.

The competition is a meta-learning challenge built from synthetic binary-classification datasets. A submitted configuration is evaluated on its ability to inspect a previously unseen dataset, train models within the evaluation limits, and select predictions that generalize well. Performance is measured with ROC AUC.

This repository contains:

- concise competition and dataset notes;
- reproducible experiment summaries;
- public leaderboard score history;
- public Kaggle Code references for completed scored experiments.

## Final status

The competition submission period ended on 2026-08-06 at 23:59 UTC. The final leaderboard result was **0.780**, placing Kun Zhang **79th**; Kaggle competition metadata reported 570 teams at close. The best displayed public score in this project was **0.822**.

The final completed scored run, `s027`, is Kaggle submission `55304471`. It prioritizes a sample-submission-declared prediction column when several train-only columns would otherwise make target inference ambiguous, while preserving preferred-name and single-train-only precedence. Five targeted schema cases passed, all 32 visible-task comparisons across two pandas string-inference modes were unchanged, and a synthetic end-to-end test completed four model families and eight candidates with zero model errors. The 12,818-byte archive differs from `s026` only in `skills/robust-tabular/scripts/common.py`; its SHA-256 is `62d072aeae10fcb1762f1093ef40a5f741e09c32d813d1e0ab0987eeefe1fb3e`. Its public score matched the retained best at displayed precision, supporting a target-inference compatibility repair without establishing a leaderboard improvement. All twenty-seven scored runs have corresponding public Kaggle Code records, and this repository is finalized as the public project record.

## Repository layout

- `docs/competition_notes.md` — public rules, metric, and task summary.
- `data/README.md` — data provenance and redistribution boundary.
- `experiments/experiment_log.md` — chronological experiment ledger.
- `results/public_scores.csv` — public leaderboard observations.
- `results/s001_meta_validation_summary.csv` through `results/s004_meta_validation_summary.csv` — aggregate validation statistics across the sixteen visible tasks.
- `solutions/` — public experiment and Kaggle Code index.

Raw competition files and generated submission archives are not redistributed here. They are available from the official Kaggle competition page subject to its rules.

Original source code in this repository is released under the [MIT License](LICENSE). Competition data and organizer-supplied materials are excluded.
