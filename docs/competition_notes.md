# Competition notes

Last reviewed: 2026-07-21

## Task

The provided data contains sixteen visible synthetic binary-classification tasks drawn from a common family of data-generating processes. Evaluation uses two additional hidden tasks. Each submission is an archive with an `agent.yaml` configuration at its root and may include prompts, custom tool definitions, and reusable skills supported by the competition harness.

## Evaluation

- Metric: ROC AUC.
- Runtime environment: standard Kaggle CPU environment.
- Evaluation session limit: 60 minutes.
- Internal prediction submissions available to a configuration: up to 30 per session.
- Model-token budget: USD 2.00 per session.
- Live competition metadata reported a maximum of one leaderboard submission per day on 2026-07-21.
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

## 2026-07-19 pre-submission experiment

- A fold-local class-conditional prototype-distance view completed all eight design tasks and 40 outer folds with zero errors. It learned six negative-class and six positive-class prototypes, then fit a regularized logistic model using only 12 squared prototype distances and two fixed distance contrasts.
- Seven of eight tasks met the fixed dual-anchor correlation cap, but every standalone candidate was weaker than its anchor. Only two fixed 80/20 blends improved over their anchors; one missed the gain and correlation gates, while the other remained below its stronger manifest reference.
- No candidate passed all same-form admission requirements, so the experiment emitted 0 candidates and retained the existing reference on all eight tasks. Decision: `DESIGN_NO_GO`; no confirmation run or package change was made.

## s010 third deterministic reference replication

- With the geometric candidate rejected, the exact s002 archive was selected as an operational reference replication, not as a model improvement or expected leaderboard gain.
- Official submission row `54820563`, dated 2026-07-19 02:47:21.210 UTC, reached `COMPLETE` with public score `0.822`.
- The uploaded archive was the exact 12,381-byte s002 package with 18 ZIP entries, 12 regular source files, root `agent.yaml`, and SHA-256 `1f4495d72d5107a4a1b0c63306eb880476aaa93ca67a1af45190b8ab11ff8f0e`. Fresh official validation, ADK dry compilation, CRC, source-tree, and byte-level reconstruction checks passed.
- Public Kaggle Code version 1 at `beicicc/deterministic-portfolio-replication-s010` reached `KernelWorkerStatus.COMPLETE`, reproduced the scored package byte for byte, and was anonymously accessible.
- Interpretation: s010 matched s002, s008, s009, and the retained public best at displayed precision. This remains a package-level score replication and does not establish prediction identity or runtime-path identity.

## 2026-07-20 pre-submission experiments

- A fixed unsupervised random-tree leaf representation with sparse L1 logistic regression completed all eight design tasks and 40 outer folds with zero errors. Its Spearman correlations with both exact-reference top models ranged from 0.615 to 0.923, satisfying the diversity cap, but every standalone prediction and every fixed 80/20 blend was weaker than the corresponding manifest reference. It emitted 0 candidates and was rejected.
- A duplicate-group cross-validation screen found exact duplicate feature vectors in only one of the eight design tasks. That task contained 1,405 duplicate rows across 637 duplicate groups, 529 of which crossed the ordinary stratified folds. The remaining seven tasks had no exact duplicate groups, so the fixed two-task breadth requirement could not be met. It emitted 0 candidates and was rejected.

## s011 fourth deterministic reference replication

- With both new directions rejected, the exact s002 archive was selected as an operational reference replication, not as a model improvement or expected leaderboard gain.
- Official submission row `54843927`, dated 2026-07-20 03:17:59.447 UTC, reached `COMPLETE` with public score `0.822`.
- The uploaded archive was the exact 12,381-byte s002 package with 18 ZIP entries, 12 regular source files, root `agent.yaml`, and SHA-256 `1f4495d72d5107a4a1b0c63306eb880476aaa93ca67a1af45190b8ab11ff8f0e`. Fresh official validation, two ADK dry compilations, CRC, source-tree, and byte-level reconstruction checks passed.
- Public Kaggle Code version 1 at `beicicc/deterministic-portfolio-replication-s011` reached `KernelWorkerStatus.COMPLETE`, reproduced the scored package byte for byte, and was anonymously accessible.
- Interpretation: s011 matched s002, s008, s009, s010, and the retained public best at displayed precision. This remains a package-level score replication and does not establish prediction identity or runtime-path identity.

## 2026-07-21 pre-submission experiment

- A fixed tree-augmented naive Bayes categorical-dependency screen completed all eight design tasks and 40 outer folds with zero errors.
- Two fixed forms passed task-level admission, improving their manifest references by `+0.00309046` and `+0.00170354`; the mean deployed delta across all eight tasks was `+0.00059925`.
- The larger gain accounted for 64.47% of all positive gain, above the fixed 60% breadth cap. The experiment was rejected, with no confirmation evaluation or package change.

## s012 fifth deterministic reference replication

- With the categorical-dependency candidate rejected, the exact s002 archive was selected as an operational reference replication, not as a model improvement or expected leaderboard gain.
- Official submission row `54866430`, dated 2026-07-21 01:50:15.413 UTC, reached `COMPLETE` with public score `0.822`.
- The uploaded archive was the exact 12,381-byte s002 package with 18 ZIP entries, 12 regular source files, root `agent.yaml`, and SHA-256 `1f4495d72d5107a4a1b0c63306eb880476aaa93ca67a1af45190b8ab11ff8f0e`. Fresh official validation, dry compilation, CRC, source-tree, and byte-level reconstruction checks passed.
- [Public Kaggle Code Version 2](https://www.kaggle.com/code/beicicc/deterministic-portfolio-replication-s011?scriptVersionId=336820326) reached `KernelWorkerStatus.COMPLETE`, reproduced the scored package byte for byte, and was anonymously accessible. Version 1 remains the s011 record.
- Interpretation: s012 matched s002, s008, s009, s010, s011, and the retained public best at displayed precision. This remains a package-level score replication and does not establish prediction identity or runtime-path identity.
