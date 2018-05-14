# Perceptrons
- [ ] Initial move through
- [ ] Review

Perceptron algorithms deal with classification, and are the building block of neural networks.

## Boundaries
- In a simple case, we usually can find a decision boundary equation and classify points based on whether they are above or below the boundary. https://cl.ly/2r0H082d163u

### High Dimensions
- We can generalize this into higher boundaries. In training, we aren't concerned with the number of features. Rather, we want to learn the weights of the boundary. In an n dimensional space, we have a boundary in the form of an  n-1 dimensional hyperplane.

## Perceptron
- A graphical way of representing our boundary equation. The input nodes represent all features, the edges represent the weights. The main node does the check of whether the resulting function is 0 or not.  https://cl.ly/1u0m0S2p1d2S https://cl.ly/0v3G3o1T1G3r
- Perceptrons are particularly good for implemening logical operators

### Training a Perceptron
- We want a perceptron to teach itself its weights and biases based on the correct solutions.
- Therefore, we can look at the misclassified points of a perceptron and adjust the weights/bias so that the boundary represented by the perceptron moves closer to the misclassified points. One way to do this is to subtract or add (depending on how the point was misclassified) the coordiates of the point (multiplied with the learning rate) from the original boundary to get the new boundary. https://cl.ly/1E3Q1S092B2S

