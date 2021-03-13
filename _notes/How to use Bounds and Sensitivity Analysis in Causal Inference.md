---
title: How to use Bounds and Sensitivity Analysis in Causal Inference
tree_state: 🌱
---

If we create a confidence interval that has any amount of bias, the confidence interval will have its **coverage probability** $\rightarrow 0$ as $n \rightarrow 0$ (where $n$ is sample size).

**coverage probability** is the proportion of the time that the confidence interval contains the true value of interest.

In Causal Inference if our assumptions about unconfoundedness or posivity are incorrect, then we will probably have a biased estimator of the treatment effect.

## So how can we unbias a treatment effect estimate?

- Using bounds are useful because they allow us to drop a bunch of our assumptions, but they are often criticized as having bounds that are too conservative. Relavant readings:
	- Imbens & Manski (2004)
	- Chernozhukov, Hong, & Tamer (2007)
- Sensivitity bounds are useful if we can make some educated guess at the extent of unobserved confounding, rather than dropping the ignorability/exchangeability assumption entirely and looking at worst case

### If a different treatment effect is identifiable by the observed data then we can estimate that treatment effect and then use it to bound the treatment effect of interest
- Suppose the local **average treatment effect (LATE)** is identifiable (this is the average treatment effect for a specific group like the compliers, or always takers when using an instrumental variable)
	- Then you can construct bounds for the true ATE from the LATE
