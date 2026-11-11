# econ3916-lab16-regularization
# Regularization: Buying Bias to Sell Variance

## Objective
I tested whether adding a penalty to a linear regression, which adds some bias to the estimates, lowers test error enough to be worth it when there are many more predictors than the data can support.

## Methodology
- I simulated a design with 200 predictors, of which only 5 had a real effect, and used 105 training rows.
- I fitted OLS, LASSO and Ridge to the training data and compared their test MSEs.
- I traced the LASSO path to see at which step the five true predictors and the first noise variable entered.
- I chose the LASSO penalty by 5-fold cross-validation, fitting the scaler inside every fold on that fold's training data only.
- I scored LASSO's selected predictors against the known truth, counting true predictors found and false positives.
- I gave LASSO and Ridge two near-duplicate predictors to compare how each one shared the weight between them.
- I wrote my own prompt asking an AI for the cross-validation loop and checked its chosen lambda and CV MSE against my own function.

## Key Findings
Cross-validation chose lambda = 0.1995, with a CV MSE of 1.5502.
The AI's cross-validation loop took 2 rounds. Checked against my own function, its chosen lambda and CV MSE matched mine exactly, on both the full grid of 21 penalties and on every second penalty.
