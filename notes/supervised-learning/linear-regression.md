# Linear Regression
- [ ] Initial Notes
- [ ] Review

## Conceptually
Conceptually, linear regression is a supervised learning technique that tries to answer the question 'how much'.

We can think of linear regression training as trying to move a line such that it best fits the training points.

## The Absolute Trick
- If we think about training a linear regression model as moving a line, we can use the absolute trick for training. Specifically, we adjust the weights of parameters of the line to get the line closer to a point, using a learning rate alpha. https://cl.ly/150M1k14112A

## The Square Trick
- We can move the line by considering the change in y intercept as well. https://cl.ly/3h0F2X0o1C1A

## Gradient Descent
- A technique to estimate the weights of our parameters. Gradient descent involves finding the gradient of the error function and moving in the direction that minimizes the error. Mathematically: https://cl.ly/2G430W3a0o0E. We can do this repeatedly until we converge at a certain point.

### Error Function
- We need error functions to find the negative gradient of. Two common ones are mean absolute error and mean squared error

#### Mean Absolute Error
- https://cl.ly/063J2D0U2b33
- In other words, the average difference from y to y_hat, where y is the true value and y_hat is the predicted y value.

#### Mean Squared Error
- https://cl.ly/2m2y1M463L3s
- In other words, half the average of the sum of squared errors. We no longer need to think about taking the absolute value of the difference.

### Gradient Descent Versus Using the Two Tricks
- It turns out, doing either of these is the same thing. The Mean Absolute Error function is the same as the absolute trick, and the Mean Square Error is the same as the square trick.

### Batch versus Stochastic Gradient Descent
- Stochastic Gradient Descent involves applying the squared trick at a single point, updating the weights, and then applying it to the next point.
- Batch Gradient Descent involves applying the the squared trick to all points, adding them, then updating the weights. 
- Both of these methods are computationally slow with large data
- Mini-Batch Gradient Descent is a compromise, where we split our points into little, even batches. Then we go through each batch, compute the error, then update the weights and move on.

## Multi-dimensional Linear Regression
- We try to predict an outcome based on n input variables, or features.

## Closed Form Solution
- We can calculate the derivative of the error function with respect to all the weights and set the results to 0, so that we have one equation per weight. We then are able to solve the system of equations using linear algebra, like so https://cl.ly/0C2D2s1z3i3F. However, as the number of dimensions increases, this becomes computationally expensive. Gradient Descent is a solution to this problem because it allows us to approximate a solution relatively cheaply.

## Linear Regression Caveats
- Works best when data is linear
- It's sensitive to outliers, because it attempts to find the best fit line

## Polynomial Regression
- We aren't restricted to a linear equation, we can do something very similar for polynomial functions

## Regularization
- Works for regression and classification
- Regularization is a technique that helps us make sure a model doesn't overfit the data
- Essentially, because simpler models generalize better than complex ones, we want to punish complex models. We can do this by taking the coefficients of the models into account.

### L1 Regularization
- When training, we can take the absolute sum of the coefficients and add that to the error. https://cl.ly/0d3d2A293w3p

### L2 Regularization
- Instead of adding the absolute values, we add the squares of the coefficients. https://cl.ly/083D1a2F3R3g

### Lambda Parameter
- The problem is that we might punish the complicated model too much or too little. We need to fine tune how much to punish the model, and we can do that by multiplying the regularization error by some Lambda. A large lambda will favor a simple models, and a small lambda will favor a complex model. Here is an image of a large lambda being applied to the green error, which represents the error from adding up coefficients. https://cl.ly/0l1X1G1y331P

Here are the differences between the two https://cl.ly/303b0f3u3s2c
