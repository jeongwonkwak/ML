# Model Evaluation

## Confusion Matrix
- A confusion matrix allows us to view four different possible predictions: true positive, true negative, false positive, and false negative

## Accuracy
- Accuracy (the percentage of correctly classified points) can be a poor predictor of a model's success. Consider a credit card fraud detection model, where there's perhaps 9900 good transactions and 100 bad transactions. A model that blindly predicts that all transactions are good will be 99% accurate, but it will miss all of the bad transactions.

## False Negatives and Positives
- False negatives are predictions that classify something as negative but are actually positive (for example, a prediction that a transaction isn't fraudulent when it actually is). False positives are predictions that classify something as positive when it's actually negative (for example, a prediction that a good credit card transaction is fraudulent).

## Precision
- Out of all the positively labeled cases, how many are truly positive?

## Recall
- Out of all the truly positive cases, how many are labeled positive?

## F1 Score
- The F1 score is the harmonic mean of the precision and recall, which will skew towards the lower of the two. It provides a single score of the model. It can be calculated as 2*precision*recall / (precision + recall).
- If either precision or recall are 0, F1 will be 0. 

## F-Beta Score
- A more generalized form of the F1 score that allows us to give more importance to either precision or recall. A Beta = 1 will be an F1 score, which evenly considers both precision and recall. A beta between 0 and 1 will favor precision, whereas a beta greater than 1 will favor recall. It can be calculated as (1 + Beta ^ 2) * precision * recall / (Beta^2 * precision + recall)

## Receiver Operating Characteristic (ROC) Curve
- Basically, we can split the data different ways and observe the true positive / all positive and true negative / all negative. We can then plot these values and find a curve. Taking the area of the curve, we'll generally get values between 0.5 and 1. 0.5 corresponds to a random split of the data, 1 corresponds to a perfect split. Note: I need to revisit the ROC curve.

## Absolute Mean Square Error
- A common measurement of error in regression models.

## R2 Score
- A measurement of the goodness of a regression model. Specifically, it's calculated as 1 - (MSE of model / MSE of simplest possible model) (where the simplest possible model is just an average of all the values). R2 will be close to 1 if the model is good. If R2 is close to 0, the model is bad.
- This is also refered to as the coefficient of detemination. It is very useful for regression analysis. This value can be interpreted as the percentage of the variance of the dependent variable that can be predicted from the independent variable.

