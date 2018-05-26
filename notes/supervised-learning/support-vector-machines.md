# Support Vector Machines
An SVM is an algorithm that tries to find the hyperplane that best separates the data. Generally speaking, SVMs pick decision boundaries that are furthest away from the points.

## Maximizing the Margin
- We can think of our desired split in data as maximizing the moargin of space between the two sets of points. For e.g., https://cl.ly/0O420c2E2V2K
- Of course, data isn't usually prettily split like that. Instead, there are bound to be missclassified points on either side of the decision boundary, as well as points within the margin. We want to avoid both those situations, so our new error function will be something to the affect of Error = Classification Error + Margin Error. https://cl.ly/1s0i332d370B

### Building an error function

#### Perceptron Algorithm
- We start with a line through the data, and we want to adjust it to fit the data better
- In a nutshell, we want to punish each misclassified point based on how far away it is from the decision boundary.
- Remembering that a line is defined as Wx + b = 0, we can evaulate where the point is in relation to the line and set that as the error. In the diagram, the two red points would have errors of 0.5 and 2.5, and the blue points would have errors 1 and 2 (because the error is absolute value):https://cl.ly/031o3a2g2e2i

#### (SVM) CLASSIFICATION Error
- Now we want to do something similar, but instead of misclassifying only what's on the wrong side of the line, we want to punish what's in the margins as well: https://cl.ly/2H292X1b073T

#### (SVM) MARGIN Error
- We prefer a larger margin, so we'll have an error function that punishes small margins more than large margins
- The margin is defined as 2 / abs(W), where W is in Wx + b = 0. Therefore, by setting Error = abs(W)^2, we have something that, if we minimize it, we will have larger margins.

#### Minimizing the Error
- We can minimize our error function, Error = Classification Error + Margin Error, by using gradient descent

### The C Parameter
- The C parameter is a hyperparameter that allows for flexibility in how willing we are to have errors for wider margins
- Specifically, Error = C * Classification Error + Margin Error. A large C will lead to more sensitivity to classification errors, and therefore less acceptance of errors and more acceptance of smaller margins. A small C will lead to more sensitivity to margin errors, and therefore will allow classification errors for larger margins.

## Polynomial Kernel
- If lines aren't good enough due to the structure of the data, we can use the kernel trick. Essentially, we add a new dimension to our data and find a function that would separate the data in the new space. We can then find a boundary to separate the data using an SVM.
- E.G. https://cl.ly/3I2Z290G2Z1Z

## RBF Kernel
- RBF - Radial Basis Function
- We can make an RBF function for each point in a space, and then simply multiply the RBFs of one class by -1. Then, we can add all the functions together, project the points onto the curve, and use an SVM to separate the points in this higher dimension. The intersection between the summed function and the boundary can be projected onto our lower dimension to show the separation points
- We aren't restricted to multiplying and subtracting curves: we can actually give weights to the radial basis functions
- We can take the height of each point on each curve and project those coordinates onto a higher dimension, then use an SVM to split the data. https://cl.ly/1V0d3D020R0A

### Tuning RBF
- We can tune how wide or narrow each radial basis is with the gamma parameter, which we tune during training. A large gamma corresponds to narrow peaks, a small gamma to wide peaks.
- Conceptually, if a peak is narrow, then it will cover less area when spliting data (it may cover less points). A wide peak will cover a larger amount of points. https://cl.ly/43471H1E122P
- Large gamma tend to overfit, small tend to underfit
- gamma determines the distance a single data sample exerts influence.
That is, the gamma parameter can be said to adjust the curvature of the decision boundary.
- The larger the gamma, the smaller the curvature.
- Gamma is defined thusly https://cl.ly/0Q1p2L1e3s1A

## RBF versus Polynomial Kernels
- In situations where a nonlinear kernel is needed, RBF is generally considered (https://stats.stackexchange.com/questions/18030/how-to-select-kernel-for-svm?rq=1) a good first choice. 
- Are there any other considerations/special cases where either kernel is better than the other?
