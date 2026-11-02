# California Housing: Explanation vs. Prediction

## Objective

This project examines the difference between explaining relationships in housing data and accurately predicting housing values using linear regression.

## Methodology

- Loaded the California Housing dataset from scikit-learn.
- Estimated a simple regression of median house value on median income.
- Added random noise predictors to compare regular and adjusted \(R^2\).
- Examined residuals for nonlinearity, unequal variance, and measurement limits.
- Created an 80/20 training and test split.
- Compared an income-only model with a full eight-feature model.
- Used coefficient confidence intervals for explanation and test RMSE for prediction.
- Investigated the dataset’s maximum-value ceiling.

## Key Findings

- A one-unit increase in median income was associated with approximately a **0.418-unit increase in median house value**, or about **$41,800**.
- The income-only model had an \(R^2\) of approximately **0.4734**.
- Adding 100 random predictors increased training \(R^2\) slightly to **0.4758**, showing why training \(R^2\) alone can reward unnecessary complexity.
- The full model achieved a training RMSE of **$71,970** and a test RMSE of **$74,560**.
- The income-only model had a test RMSE of about **$84,210**, so the full model reduced typical prediction error by approximately **$9,650**.
- AveRooms had an estimated coefficient of **−0.0381**, with a 95% confidence interval of approximately **[−0.0430, −0.0333]**.
- The dataset contained **965 districts** at the maximum reported value. Removing these observations reduced test RMSE, but changed the population described by the model.

## Conclusion

Statistical significance and predictive accuracy answer different questions. Confidence intervals are useful for evaluating estimated relationships, while performance on held-out data is more appropriate for judging predictions. A model can estimate a statistically clear relationship while still producing substantial prediction errors.
