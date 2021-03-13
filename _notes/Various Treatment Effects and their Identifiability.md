---
title: Various Treatment Effects and their Identifiability
tree_state: 🌱
---
# For Randomized Experiments
https://mattblackwell.org/files/teaching/s04-experiments.pdf

## SATE
Sample Average Treatment Effect (SATE):
$$S A T E=\tau_{S}=\frac{1}{N} \sum_{i \in S} Y_{i}(1)-Y_{i}(0)$$
Estimate of SATE:
$$\hat{\tau}_{S}=\frac{1}{N_{t}} \sum_{i: A_{i}=1} Y_{i}-\frac{1}{N_{c}} \sum_{i: A_{i}=0} Y_{i}$$
In a completely randomized experiment assignment, estimate of SATE is unbiased estimator
$$\begin{aligned}
E\left[\hat{\tau}_{S} \mid S\right] &=\frac{1}{N_{t}} \sum_{i: A_{i}=1} E\left[Y_{i} \mid A_{i}=1, S\right]-\frac{1}{N_{c}} \sum_{i: A_{i}=0} E\left[Y_{i} \mid A_{i}=0, S\right] \\
&=\frac{1}{N_{t}} \sum_{i: A_{i}=1} E\left[Y_{i}(1) \mid S\right]-\frac{1}{N_{c}} \sum_{i: A_{i}=0} E\left[Y_{i}(0) \mid S\right] \\
&=\frac{1}{N_{t}} N_{t} E\left[Y_{i}(1) \mid S\right]-\frac{1}{N_{c}} N_{c} E\left[Y_{i}(0) \mid S\right] \\
&=E\left[Y_{i}(1)-Y_{i}(0) \mid S\right]=\frac{1}{N} \sum_{i \in S} Y_{i}(1)-Y_{i}(0)=\tau_{S}
\end{aligned}$$

## PATE
Population Average Treatment Effect (PATE)
$$P A T E=\tau=E\left[Y_{i}(1)-Y_{i}(0)\right]$$
In a completely randomized experiment assignment, since SATE is an unbiased estimator, so is PATE:
$$E\left[E\left[\hat{\tau}_{S} \mid S\right]\right]=E\left[\tau_{S}\right]=\tau$$




## Now Adding Covariates
We could use the simple difference-in-means estimator, which is root-n consistent and asymptotically normal under no modeling assumptions; however it completely ignores covariate information and so may be quite inefficient relative to other estimators.Alternatively we could model the re-
gression function and use the plug-in estimator. However if we use parametric models to achieve root-n rates and small confidence intervals, we are putting ourselves at great risk of bias due to model misspecification; on the other hand, if we model the regression functions nonparametrically, letting the data speak for themselves, then we will typi-
cally suffer from the curse of dimensionality and be subject to slow rates of convergence, and at a loss for confidence intervals and inference.

## Why we must use sample splitting
There are two reasons for doing sample splitting: the first is that the analysis
is more straightforward, and the second more important reason is that it prevents
overfitting and allows for the use of arbitrarily complex estimators μba (e.g., random
forests, boosting, neural nets). Without sample splitting, one would have to restrict
the complexity of the estimator μba via empirical process conditions (e.g., via Donsker
class or entropy restrictions). Intuitively, this is because the estimator ψb is using the
data twice: once to estimate the unknown function μa and once to estimate the bias
correction. Sample splitting ensures that these tasks are accomplished independently.

Theorem 3.2 is a simple but powerful result. It shows the doubly robust estimator
is exactly unbiased, for any choice of regression estimator μba. Hence, although the
estimator ψb exploits covariate information, its bias is not at all affected by accidentally
misspecified models or biased regression estimators with slow convergence rates.

We have learned the surprising result that the sample-split doubly robust estimator
is exactly unbiased for any choice of regression estimator μba, and root-n consistent
and asymptotically normal as long as μba converges to some fixed function at any rate.
As would be expected, the efficiency of the doubly robust estimator depends on the
probability limits μa that the regression estimators μba converge to. This raises some important questions:


## Moving to Conditionally Randomized Experiments
In conditionally randomized experiments, the randomization probabilities can differ by
covariate values, e.g., in a stratified Bernoulli experiment one sets

$$\mathbb{P}\left(A=1 \mid X=x, Y^{a}\right)=\pi(x)$$

The doubly robust estimator is still consistent regardless of a misspecified outcome model, because we know the true propensity scores:

$$\mathbb{P}_{n}\left[\left\{\widehat{\mu}_{1}(X)-\widehat{\mu}_{0}(X)\right\}+\left\{\frac{A}{\pi(X)}-\frac{1-A}{1-\pi(X)}\right\}\left\{Y-\widehat{\mu}_{A}(X)\right\}\right]$$

There are some important differences between simple Bernoulli experiments and
conditionally randomized designs, however. First, the difference-in-means estimator is
no longer a valid estimator, since it is no longer the case that $A \perp Y^a$ or $A \perp (X,Y^a)$.


## Moving to Observational Studies
Importantly, no unmeasured confounding $A \perp Y^a \mid X$ means the observational study
is actually a conditionally randomized experiment, but one in which the randomization
probabilities