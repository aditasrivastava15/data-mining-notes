# Regression

The job is: given x, predict a number y, and measure the miss.

## One line

Predicted y = mx + b. The residual is actual y minus predicted y. Least squares minimizes the sum of squared residuals. Squaring punishes a miss of 4 more than two misses of 2, and the cost has one bottom.

The winning slope is the covariance of x and y divided by the variance of x. The intercept is mean of y minus m times mean of x. The line passes through (mean x, mean y).

Example. x is 1, 2, 3. y is 2, 3, 6. Means are 2 and about 3.667. Using averages that divide by n, variance of x is 2/3 and covariance is 4/3. Slope is 2. Intercept is about -0.333. The line is about y = 2x - 0.333.

Read the slope in units. If x is rooms and y is price in thousands, m = 40 means each extra room goes with about 40 thousand more in this data. It does not by itself prove cause. The intercept at x = 0 may be nonsense, such as a house with zero rooms. Then it is a fitting device, not a fact.

## Many inputs

Predicted y = b0 + b1 x1 + b2 x2 + ... . Each coefficient is the change when that input grows by 1 and the others stay fixed. If rooms and square feet rise together, the data cannot tell which deserved the credit. Coefficients get unstable. That is multicollinearity.

In matrix form, with a column of ones for the intercept, the normal equation gives the least-squares coefficients in one shot when columns are not redundant. It becomes numerical mush when columns are duplicates or you have more columns than rows.

## Gradient descent

Mean squared error is a valley over the coefficients. The gradient is the list of uphill slopes. Each step subtracts learning rate times that slope. Too big a rate bounces across the valley. Too small arrives late. Plot cost against step. It should fall, then flatten.

For plain linear regression, the normal equation and gradient descent aim at the same coefficients. Descent still matters when you change the cost, add a penalty, or move to logistic regression.

## Curves and small formulas

Polynomial regression adds columns x squared, x cubed, and so on, then fits a line in those columns. A high order can hit every training dot and swing between them.

Ridge adds a penalty on the sum of squared coefficients. They shrink toward 0 and are not forced to be exactly 0. Lasso penalizes the sum of absolute coefficients. Some become exactly 0, so lasso also drops features. Choose the penalty strength with a held-out score.

## Support vector regression

Ordinary least squares charges every residual. SVR draws a tube of width epsilon. Residuals inside are free. Residuals outside are paid for. A soft margin adds slack so a few extremes do not make the problem impossible. A kernel bends the space when the relationship is not straight.

## Scores

MAE is the average absolute residual, in y's units. MSE averages squares. RMSE is its square root, still angrier at big misses.

R squared is the fraction of y's variance the model removed. 1 is perfect. 0 matches predicting the mean. It can be negative on a test set. R squared rises when you add junk columns. Adjusted R squared charges for extra columns.

**Check.** Training R squared is 0.99 with a degree-12 polynomial on 15 points. Test MAE is worse than predicting the training mean. What happened, and which remedies apply?
