# Model Card — AI Labor Vulnerability Predictor

## Model Summary

The final model predicts an AI Labor Vulnerability Score from workforce,
industry, salary, task, and economic indicators.

## Final Pipeline

- Algorithm: Extra Trees Regressor
- Preprocessing: imputation, scaling, and one-hot encoding
- Numeric features: 23
- Categorical features: 3
- Train/test split: 12,000 / 3,000
- Cross-validation: 5-fold
- Hyperparameter optimization: RandomizedSearchCV

## Performance

| Metric | Value |
|---|---:|
| Test R² | 0.9572 |
| CV R² | 0.9584 |
| CV standard deviation | 0.0072 |
| RMSE | 1.7517 |
| MAE | 1.2803 |

## Leakage Control

Seventeen reconstruction and target-adjacent variables were removed before
training. Every model was evaluated through the same preprocessing pipeline.

## Benchmark

Nine regression algorithms were compared, including linear, tree-based, and
boosting methods. Extra Trees produced the strongest final performance.

## Intended Use

- Workforce analytics experiments
- AI-employment risk exploration
- Portfolio and educational demonstrations
- Scenario analysis and early risk screening

## Out-of-Scope Use

The model should not be used as the sole basis for hiring, termination,
compensation, promotion, or other high-impact employment decisions.

## Limitations

- The dataset contains synthetic or reconstructed components.
- Predictions may not generalize to unrepresented countries, roles, or industries.
- A high model score does not establish causal relationships.
- External validation and fairness testing are required before operational use.
