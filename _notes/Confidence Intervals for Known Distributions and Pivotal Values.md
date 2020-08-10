---
title: Confidence Intervals for Known Distributions and Pivotal Values
tree_state: 🌱
---

A $$1-\alpha$$ confidence interval for $$\theta$$ is an interval  $$(L,U)$$ where we have the following:

$$L=g_{L}\left(X_{1}, \ldots, X_{n}\right) \text{ and } U=g_{U}\left(X_{1}, \ldots, X_{n}\right) \text{ such that } P(\theta \in(L, U)) \geq 1-\alpha$$

- The confidence interval itself is random, since $L$ and $U$ are functions of random variables
- The parameter $$\theta$$ is not random.
- A confidence interval is a probability statement that a random interval captures a fixed parameter.

### Pivotal quantity

A random variable $$V = g(X_1,\ldots, X_n,\theta )$$ is a pivotal quantity if its distribution does not depend on the unknown parameter $$\theta$$

### Finding Confidence Intervals

1. Find a pivotal quantity $$V$$
2. Choose $$a$$ and $$b$$ such that $$P(a<V<b) \geq 1-\alpha$$ 
    - This can be done by choosing $$a$$ and $$b$$ such that $$P(V<a) = P(V>b) = \frac{\alpha}{2}$$
3. Could also do something very similar for a one-sided confidence interval (just need either $$a$$ or $$b$$)