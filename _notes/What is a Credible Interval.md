---
title: What is a Credible Interval
tree_state: 🌿
---

A credible interval is the Bayesian equivalent of the confidence interval where the estimated interval is dependent on the prior distribution. See [[Confidence Intervals for Known Distributions and Pivotal Values]] to learn about what a confidence interval is.

- In confidence intervals we treat the parameter as a fixed value and the bounds as random variables
- In credible intervals, the estimated parameter is treated as a random variable while the bounds are considered fixed

Any random variable following the posterior distribution $$\pi(\theta|y_1,\ldots, y_n)$$ will fall in the credible interval with probability $$1-\alpha$$

$$\int_a^b \pi(\theta | y_1,\ldots, y_n) d \theta=1-\alpha \Longrightarrow P\left(a \leq \theta \leq b | y_{1}, \ldots, y_{n}\right)=1-\alpha$$

- Conceptually, probability comes into play in a frequentist
confidence interval **before** collecting the data.
	- Ex: there is a 95% probability that we will collect data that produces an interval that contains the true parameter value.
-  Probability comes into play in a credible
interval **after** collecting the data
	- Ex: based on the data, we now think there is a 95%  probability that the true parameter value is in the interval.
	
## Here is an Example Problem:
Interested in the proportion of the population of American college students that sleep at least eight hours each night $\theta$.
- Suppose a random sample of 27 students from UF, where 11 students recorded they slept at least eight hours each night
- Suppose that $X \sim \text{Binomial}(27,\theta)$
- Let's assume we have a prior on $\theta$ where $\theta \sim \text{Beta}(3.3,7.2)$.

Thus, the posterior distribution (which we know from  [[Why are Conjugate Priors Useful]]) is:
- $\theta \mid (11,27) ∼ \text{Beta}(11 + 3.3, 27 − 11 + 7.2) = \text{Beta}(14.3, 23.2)$

Suppose now we would like to find a 90% credible interval for $\theta$ with equal probability in each tail
- So, we want to find $a$ and $b$ such that $P(\theta < a|x) = 0.05$ and $P(\theta > b|x) = 0.05$
	- We can solve this by taking the cdf of the Beta posterior up to the lower bound:
		- $\int_0^a \text{Beta}(14.3, 23.2) d\theta = 0.05$
	- Then for the upper bound
		- $\int_d^1 \text{Beta}(14.3, 23.2) d\theta = 0.05$
- These values are extremely difficult to calculate by hand (who knows how to integrate the Beta distribution?) so we can just plug our values into the beta cdf in R to find what values $\theta$ value will give us a cdf value (area under pdf) of 0.05 (for $a$) and 0.95 (for $b$).
```
a = 3.3
b = 7.2
n = 27
x = 11
a.star = x+a
b.star = n-x+b
c = qbeta(0.05,a.star,b.star)
d = qbeta(1-0.05,a.star,b.star)
```

This gives us $c = 0.256$ and $d = 0.514$ so our credible interval is $(0.256, 0.514)$

## Credible intervals are not unique on a posterior distribution. Methods for defining a suitable credible interval include:
- Choosing the narrowest interval, which for a unimodal distribution will involve choosing those values of highest probability density including the mode (the maximum a posteriori). This is sometimes called the highest posterior density interval (HPDI)
- Choosing the interval where the probability of being below the interval is as likely as being above it. This interval will include the median. This is sometimes called the equal-tailed interval.
- Assuming that the mean exists, choosing the interval for which the mean is the central point.
