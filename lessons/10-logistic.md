# Logistic regression

This is classification. The name says regression because the inner score is a line.

A straight line is a bad probability. It runs below 0 and above 1. Logistic regression keeps z = b0 + b1 x1 + ..., then squashes z with the sigmoid:

1 / (1 + e to the -z)

Large positive z becomes a probability near 1. Large negative z becomes near 0. Zero becomes 0.5.

The usual decision is at 0.5, which is where z = 0, a straight cut. Move the threshold when false alarms and misses have different costs.

Squared error is a poor cost here. Log loss charges -log(p) when the true class is 1, and -log(1 - p) when it is 0. Predicting 0.9 for a true 1 is cheap. Predicting 0.01 is expensive.

There is no normal equation. Gradient descent on log loss updates each coefficient by learning rate times (predicted probability minus actual 0 or 1) times that input. A matched prediction barely moves. A confident mistake moves a lot.

If s is the sigmoid of z, its slope is s times (1 - s). Steepest at 0.5, almost flat near 0 and 1.

## How the lessons lock

| If you are about to | Do this first | Then judge with |
|---|---|---|
| Cluster | Pick a meaningful distance and scale columns | A group you can name, plus SSE or a density check |
| Classify | Hold out labels before fitting or scaling stats | Precision, recall, ROC |
| Regress | Plot y against each x | Test MAE and adjusted R squared |
| Reduce dimensions | Standardize | Explained variance, or a second run of the map |
| Use text | Tokenize, stem, stop, then tf-idf | The same classifier scores as any other table |
