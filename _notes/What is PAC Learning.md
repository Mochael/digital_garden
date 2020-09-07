---
title: What is PAC Learning
tree_state: 🌱
---

The probability that the hypothesis, $h$, that we find with $m$ training examples is probably (with probability $\geq 1 - \delta$) approximately (with $err_D(h)\leq \epsilon$) correct. This is equivalently expressed below:

$$P(err_D(h)\leq \epsilon) \geq 1-\delta, \text{ where } \ err_D(h) = err_{true}(h) - err_{train}(h) $$

## VC Dimension

The VC dimension is the maximal number $d$ such that there exists a set of $d$ points that is shattered by the class of model classifiers. It doesn't mean that every set of points must be shattered!
- **Shattered** means that for every configuration of positive/negative labels for the points, the class of models can correctly classify every point in each set of configurations

### Example
Suppose we are looking at the class of models which are circles in $\mathbb{R}^2$ and points within the circle are labeled positive and points outside the circle are labeled negative.
- If we plot 3 collinear points in 2d, then there is no way to make a circle that can correctly classify all 3 points: think about if the middle point is negative and the two other points are both positive.
- However, if we consider the set of 3 points that lie on the corners of an equilateral triangle, then we will be able to make a circle that can correctly classify this set of points for any configuration of positive and negative labels. So we can shatter 3 points, but there is no set of 4 points that can be shattered by this class of circles so the VC dimension of these circles is 3.