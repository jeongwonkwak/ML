# Decision Trees
- Decision Trees are another form of classificiation algorithm
- A Decision Tree is basically a series of conditionals that determine a class

## Entropy
- Not a scientific definition, but an idea of entropy is that the more homogeneous a set it, the less entropy it has.
- Entropy (in the case of a two color system) can be defined as such (the denominator (m-n) should be (m+n)): https://cl.ly/0G0z182T3D3M. Note that if either m or n is 0, aka only one color exists, entropy will be the negative log of 1, which is 0.

## Information Gain
- When we split data into different subgroups, we can think about the information gain of the split (that is, how much more do we know about the data after the split compared to before the split). If both subgroups are just as heterogeneous as their supergroup, we really haven't learned anything new about the data from the split, and information gain is 0. If, however, the splt completely divided the data, then we know a lot from that split, and information gain is 1. 
- Mathematically speaking, Information Gain = Change in Entropy. Specifically, if there are m items in the first child group and n in the second child group, we have the following formular for Information Gain: https://cl.ly/1l3H2C2X341C

## Building a Decision Tree
- Basically, when building a decision tree, we split based on the feature that will result in the highest information gain, and we continuously do this until we've come to a tree.

## Problems with Decision Trees
- Due to their nature of splitting data, decision trees tend to overfit a lot. This seems to happen especially when we have a lot of columns. The solution to this is using random forests.

## Random Forests
- In order to avoid overfitting, we will make several smaller trees, each created by randomly selected a subset of columns. Then, each tree will be used when trying to classify a case, and the outcome with the most trees will be the classification. https://cl.ly/0z0O3M3M0v2J
- Note that there are better ways to split the data than simply randomly choosing columns, and we'll look at those later on.

## Hyperparameters for Decision Trees
- Maximum Depth: We can set the maximum depth of the tree as a hyperparameter. A tree of max length k will have at most 2^k leaves. A small max depth can lead to underfitting which a large max depth can lead to overfitting.
- Minimum Number of Samples per Leaf: We can avoid the situation where one leaf has a single sample whereas the other has almost all others. A high min number of samples per leaf can contribute to underfitting, and a low number of samples per leaf can contribute to overfitting.
- Minimum number of samples per split: This is the same as min number of samples per leaf but applied to any split of any node in the tree.
- Maximum number of features: Continuously having to go through a large number of features to find the best information gain during each iteration of building a tree is time consuming, so we can limit the number of features we consider at each stage. If this is higher, we're very likely to find a good feature (not necessarily the perfect one) to split on, but it will be most time consuming. A smaller set, however, will speed up our calculations but will be less likely to find a good feature.


