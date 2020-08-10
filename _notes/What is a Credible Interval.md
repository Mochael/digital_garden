---
title: What is a Credible Interval
tree_state: 🌱
---

A credible interval is the Bayesian equivalent of the confidence interval where the estimated interval is dependent on the prior distribution. See [[Confidence Intervals for Known Distributions and Pivotal Values]] to learn about what a confidence interval is.

- In confidence intervals we treat the parameter as a fixed value and the bounds as random variables
- In credible intervals, the estimated parameter is treated as a random variable while the bounds are considered fixed

Any random variable following the posterior distribution $$\pi(\theta|y_1,\ldots, y_n)$$ will fall in the credible interval with probability $$1-\alpha$$

$$\int_{\mathcal{C}} \pi(\theta | y_1,\ldots, y_n) d \theta=1-\alpha \Longrightarrow P\left(a \leq \theta \leq b | y_{1}, \ldots, y_{n}\right)=1-\alpha$$