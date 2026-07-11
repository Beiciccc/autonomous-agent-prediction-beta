# Experiment log

Scores in this ledger are copied from completed Kaggle submission rows. Validation-only work is recorded only when it is needed to interpret a scored experiment.

| ID | Submitted (UTC) | Hypothesis | Validation | Kaggle submission | Public score | Delta vs best | Public code | Decision |
| --- | --- | --- | --- | ---: | ---: | ---: | --- | --- |
| s001 | 2026-07-10 16:07:13 | A fast fallback followed by a diverse cross-validated portfolio and rank blending should improve reliability and model-family coverage. | Official dry compilation passed; sixteen-task simulation: mean Private AUC 0.80369, lower quartile 0.75801, zero model errors. | 54533337 | 0.822 | — | [`solutions/s001`](../solutions/s001) · [Kaggle Code](https://www.kaggle.com/code/beicicc/robust-tabular-portfolio-submission) | Retain as the initial scored baseline. |
| s002 | 2026-07-11 12:48:44 | Uniform five-fold evaluation plus native-categorical LightGBM and strictly OOF-gated weighted/top-three rank candidates should improve aggregate robustness without changing the proven selection stage. | Official dry compilation passed; sixteen-task simulation: mean Private AUC 0.80409, lower quartile 0.75812, zero model errors; maximum portfolio runtime 143.8 s. | 54571974 | 0.822 | 0.000 | [`solutions/s002`](../solutions/s002) · [Kaggle Code](https://www.kaggle.com/code/beicicc/five-fold-weighted-portfolio-submission) | Matched s001; retain both, with s001 remaining the earlier scored reference. |
