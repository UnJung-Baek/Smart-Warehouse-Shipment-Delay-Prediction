# Competition Context

Competition: Smart Warehouse Shipment Delay Prediction

DACON URL: https://dacon.io/competitions/official/236696/overview/description

## Objective

Predict `avg_delay_minutes_next_30m`, the average shipment delay in minutes over the
next 30 minutes, from smart warehouse operation snapshots.

The data describes simulated AMR-based warehouse scenarios with order inflow, robot
operation, battery/charging state, congestion, packing bottlenecks, environment,
staffing, and warehouse layout features.

`layout_info` has already been merged into `train.csv` and `test.csv` in this project.
Do not expect or require a separate `layout_info.csv`.

## Data

- `data/train.csv`: training data with `avg_delay_minutes_next_30m`.
- `data/test.csv`: test data without the target.
- `data/sample_submission.csv`: required submission format.
- ID column: `ID`
- Target column: `avg_delay_minutes_next_30m`

## Evaluation

- Official metric: MAE
- Public leaderboard: sampled 30% of test data
- Private leaderboard: remaining 70% of test data
- Lower score is better.

## Rules And Constraints

- Final submission must match `sample_submission.csv` columns and row order.
- Remote model APIs are not allowed for final modeling code; models must run locally.
- External training data is allowed, but test data must not be used for training.
- Daily submissions are limited, so keep a local validation record for each attempt.

## Current Known Result

- `outputs/submission_latest.csv`
- Public score: `11.2360866528`
- Notes: first portable LightGBM fallback submission from Auto_Dacon.
