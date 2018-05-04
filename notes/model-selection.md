# Model Selection

- [X] Initial population of notes
- [ ] Second read through and research

## Types of Errors
- There are two kinds of errors that we can make in machine learning: underfitting (or oversimplifying the problem) and overfitting (or overfitting the problem).

### Underfitting
- Tends to do poorly on the training set
- Known as an error due to bias

### Overfitting
- Tends to do well on the training set but poorly on the testing set
- Known as an error due to variance

## Model Complexity Graph
- We can look at models of varying polynomial degrees and plot their training and testing misclassifications/errors. The dotted line in this image is of validation error, whereas the solid line is training error. Notice that the model on the left is underfit (high training and validation error), whereas the model on the right is overfit (low training but high validation error). The middle model is just right. https://cl.ly/3g0Z1c0i0Q3a

### Cross Validation
- Because we are never allowed to use our testing data to train our model, we can't use it to decide if a model is over or under fitting. Rather, we need to check the fit of the model first with a cross validation set of data. At the very end we can finally test with our testing data.

### K-fold Cross Validation
- K-Fold Cross Validation involves splitting our data into K buckets and training our model K times, each time with a different of the K buckets used as a validation set. Then we can average the K results of cross validation to get a final model. Each time we train our model during this, it's a good idea to randomize our data. This method allows us to use the data we would normally use exclusively for validation as training data. https://cl.ly/422S2u3L1C20. NOTE: I need to revisit this in particular.

## Learning Curves
- Another tool to determine under/over fitting. https://cl.ly/3q3w3N201v0D
- Basically, we can look at models of different complexities, then plot the training and cross validation errors when using different numbers of points to train the model. As we can see in this graph, we have three cases:

### High Bias (Underfitting)
- In this case, it's generally easy to fit a few points with a very simply model, but the amount of training error gets higher and higher as more points are used in the over simplified model. However, cross validation error will always be high for simple models, so the learning curve here shows the training and cross validation curves converging at a high error.

### High Variance (Overfitting)
- In an overly complex model, we will always have low training error as the number of points increases. However, we will also continue to have high cross validation errors. The learning curves here will not converge at an error as much.

### Just Right
- Here, the curves will converge to a low point.

## Training a Model in Machine Learning
- We generally take three steps when training a machine learning model.

1) Train a bunch of models with training data
2) Use cross validation data to pick the best model
3) Use testing data to test our model

### Training a Logistic Regression Model
- We can apply these steps here:

1) Train models with different degree polynomials
2) Check the F1 scores of these models and pick the one with the highest score
3) Test with testing data to make sure it's a good model

#### Parameters and Hyperparameters of the model
- The coefficients of the different models are parameters, but the degree of the polynomials are hyperparameters (a meta parameter)

### Training a Decision Tree
- Hyperparameters in this case could be the depth of the tree
- Parameters are the nodes and leaves and thresholds, etc.

1) Learn the parameters with training data
2) Use F1 score for cross validatino
3) Test with testing data

### Training an SVM (something with multiple hyperparameters)
- How do we train a model with multiple hyperparameters?
- Answer: We can make a grid of all the value combinations of hyperparameters, pick the one with the highest F1 score, and use testing set.
- https://cl.ly/250d3G0S1r1B

### Grid Search
- If there are multiple hyperparameters that we want to compare, we might want to use Grid Search, a method that allows us to make combinations of possible hyperparameters that we can then cross-validate and select from.


