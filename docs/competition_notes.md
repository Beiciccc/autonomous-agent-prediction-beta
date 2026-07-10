# Competition notes

Last reviewed: 2026-07-10

## Task

The provided data contains sixteen visible synthetic binary-classification tasks drawn from a common family of data-generating processes. Evaluation uses two additional hidden tasks. Each submission is an archive with an `agent.yaml` configuration at its root and may include prompts, custom tool definitions, and reusable skills supported by the competition harness.

## Evaluation

- Metric: ROC AUC.
- Runtime environment: standard Kaggle CPU environment.
- Evaluation session limit: 60 minutes.
- Internal prediction submissions available to a configuration: up to 30 per session.
- Model-token budget: USD 2.00 per session.
- Final competition deadline: 2026-08-06 23:59 UTC.

The public and private leaderboard evaluations are separate sessions. The official competition pages remain the source of truth for current limits and rule changes.

## Data

Each visible task directory follows the same high-level layout:

- `train.csv` — training rows and binary target;
- `test.csv` — rows requiring probability predictions;
- `sample_submission.csv` — required output schema;
- `solution.csv` — labels and usage split for local evaluation;
- `DATA.md` — task-specific metadata.

Supporting files supplied by Kaggle include the configuration model list, local validator, evaluation runner, harness wheels, sample configuration, and environment documentation.

## Submission format

The upload is a `submission.zip` archive. Its root must contain `agent.yaml`; referenced prompts, tools, and skill directories are packaged beneath that root.

## Sources

- [Competition overview](https://www.kaggle.com/competitions/autonomous-agent-prediction-beta/overview)
- [Competition data](https://www.kaggle.com/competitions/autonomous-agent-prediction-beta/data)
- [Competition rules](https://www.kaggle.com/competitions/autonomous-agent-prediction-beta/rules)
