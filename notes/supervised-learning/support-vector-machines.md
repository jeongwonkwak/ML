# Support Vector Machines
An SVM is an algorithm that tries to find the line that best separates the data. Generally speaking, SVMs pick decision boundaries that are furthest away from the points.

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
- 
