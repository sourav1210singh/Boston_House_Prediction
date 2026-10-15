
---

## 2.3 `Boston_House_Prediction` — new file

⚠️ **Read the warning below this block before pasting.**

```markdown
# Boston House Price Prediction

A regression model predicting house prices, built with CatBoost.

## Approach

- **Model:** CatBoost regressor, hyperparameters tuned
- **Target transformation:** log transformation on price, to handle right-skew
- **Feature scaling:** standardisation
- **Validation:** Shapiro-Wilk test on the residuals to check they are normally distributed

Residual diagnostics matter here. A regression model can report a good R² while its errors are
structured, which means it is wrong in a predictable direction. Checking residual normality is
what tells you the model is actually trustworthy rather than just well-scored.

## Results

| Metric | Value |
|---|---|
| R² | 0.88 |
| RMSE | 0.13 |

## Files

| File | Purpose |
|---|---|
| `catboost_model.pkl` | Trained model |
| `catboost_info/` | CatBoost training logs and error curves |
| `requirements.txt` | Dependencies |
