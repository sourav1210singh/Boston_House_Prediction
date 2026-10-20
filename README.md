# Boston House Price Prediction

A regression model predicting house prices with CatBoost, including residual diagnostics to
check the model is actually trustworthy rather than just well-scored.

## Approach

- **Model:** CatBoost regressor with tuned hyperparameters
- **Target transformation:** log transformation on price to handle right-skew
- **Feature scaling:** standardisation
- **Validation:** Shapiro-Wilk test on the residuals to confirm they are normally distributed

Residual diagnostics matter here. A regression model can report a strong R-squared while its
errors are structured, which means it is wrong in a predictable direction. Checking residual
normality is what separates a model you can rely on from one that merely scores well.

## Results

| Metric | Value |
|---|---|
| R-squared | 0.88 |
| RMSE | 0.13 |

## Files

| File | Purpose |
|---|---|
| `boston_house_price.ipynb` | Main notebook - EDA, feature engineering, training, diagnostics |
| `boston_house_price_v2.ipynb` | Second iteration |
| `catboost_model.pkl` | Trained model |
| `requirements.txt` | Dependencies |

## Running it

```bash
pip install -r requirements.txt
jupyter notebook boston_house_price.ipynb
```

CatBoost writes a `catboost_info/` folder during training. It is regenerated on every run, so
it is gitignored rather than committed.
