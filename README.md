# MSCS_634_ProjectDeliverable_2

# Deliverable 2: Regression Modeling and Performance Evaluation

## Dataset Summary
The Customer Experience Dataset contains 1,000 records with information on:
- Customer demographics (Age, Gender, Location)
- Interaction data (Num_Interactions, Products_Purchased, Feedback_Score)
- Behavioral data (Products_Viewed, Time_Spent_on_Site)
- Outcome variable: Satisfaction_Score

## Feature Engineering
- **Engagement_Rate:** Time spent on site per interaction.
- **Purchase_to_View_Ratio:** Products purchased divided by products viewed.
- One-hot encoding applied for categorical variables: Gender and Location.

## Models Built
1. **Linear Regression**
2. **Ridge Regression**
3. **Lasso Regression**

## Model Evaluation
| Model              | R² Score | MSE    | RMSE   |
|-------------------|----------|--------|--------|
| Linear Regression  | -0.0314  | 7.9364 | 2.8172 |
| Ridge Regression   | -0.0312  | 7.9345 | 2.8168 |
| Lasso Regression   | -0.0180  | 7.8332 | 2.7988 |

- Cross-validation shows consistent R² scores across folds:
    - Linear Regression: -0.0202
    - Ridge Regression: -0.0201
    - Lasso Regression: -0.0119
- **Lasso Regression** performed slightly better in terms of R² score, but all models show very low predictive power as indicated by the negative R² values. Ridge/Lasso help with feature regularization.

## Key Insights
- The current features and models do not seem to be good predictors of customer satisfaction based on the low and negative R² scores.
- Some features like `Feedback_Score` have high correlation with `Satisfaction_Score`.
- Regularization models (Ridge/Lasso) reduce overfitting slightly compared to Linear Regression.

## Challenges & Solutions
- **Feature skew**: Some variables (e.g., `Time_Spent_on_Site`) had skewed distribution; used log transformation if needed.
- **Multicollinearity**: Ridge and Lasso regression reduce multicollinearity effects.
- Ensuring cross-validation reproducibility by using fixed random state.

