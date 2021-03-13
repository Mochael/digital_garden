---
title: How to Get the Bootstrapped Standard Error for a Parameter Estimate
tree_state: 🌱
---

Let $\hat{\theta}$ denote the estimate of our parameter (what it is), from the original sample. Then let $\hat{\theta}_{b}, b=1, \ldots, B$ denote the B estimates of $\theta$ from the bootstrap samples. The bootstrap standard error for $\hat{\theta}$ is then given by
$S E(\hat{\theta})=\sqrt{\frac{1}{B-1} \sum_{b=1}^{B}\left(\hat{\theta}_{b}-\bar{\theta}\right)^{2}}$
where $\bar{\theta}=(1 / B) \sum_{b=1}^{B} \hat{\theta}_{b}$ denotes the mean of the estimates across the B bootstrap samples.

This is the same thing as calculating the sample standard deviation, but since it is the deviation of a statistic (i.e. a mean) this standard deviation is actually a standard error.