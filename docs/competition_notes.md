# Competition notes

Last reviewed: 2026-07-18

## Task

The provided data contains sixteen visible synthetic binary-classification tasks drawn from a common family of data-generating processes. Evaluation uses two additional hidden tasks. Each submission is an archive with an `agent.yaml` configuration at its root and may include prompts, custom tool definitions, and reusable skills supported by the competition harness.

## Evaluation

- Metric: ROC AUC.
- Runtime environment: standard Kaggle CPU environment.
- Evaluation session limit: 60 minutes.
- Internal prediction submissions available to a configuration: up to 30 per session.
- Model-token budget: USD 2.00 per session.
- Live competition metadata reported a maximum of one leaderboard submission per day on 2026-07-18.
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

## 2026-07-18 pre-submission experiments

- A fold-local supervised-univariate-binning view completed all eight design tasks with 2 wins, 6 ties, 0 losses, and mean paired delta `+0.00038173`. It was rejected because one task supplied 71.99% of the positive gain, above the fixed 60% cap.
- A fixed CatBoost PairLogit ranker completed all eight design tasks and 40 outer folds with zero errors. It produced 1 win, 7 ties, 0 losses, mean paired delta `+0.00012039`, and 100% gain concentration. It failed the fixed two-win, mean-gain, and concentration gates and was not submitted.

## s009 second deterministic reference replication

- With both new directions rejected, the exact s002 archive was selected as an operational reference replication, not as a model improvement or expected leaderboard gain.
- Official submission row `54799003`, dated 2026-07-18 04:40:28.030 UTC, reached `COMPLETE` with public score `0.822`.
- The uploaded archive was the exact 12,381-byte s002 package with 18 ZIP entries, 12 regular source files, root `agent.yaml`, and SHA-256 `1f4495d72d5107a4a1b0c63306eb880476aaa93ca67a1af45190b8ab11ff8f0e`. Fresh official validation, ADK dry compilation, CRC, and byte-level reconstruction all passed.
- Public Kaggle Code version 1 at `beicicc/deterministic-portfolio-replication-s009` reached `KernelWorkerStatus.COMPLETE` and reproduced the scored package byte for byte.
- Interpretation: s009 matched s002, s008, and the retained public best at displayed three-decimal precision. This remains a package-level score replication and does not establish prediction identity or runtime-path identity.
