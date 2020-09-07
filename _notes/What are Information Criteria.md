---
title: What are Information Criteria
tree_state: 🌱
---

Information critera are measure of the quality of a statistical model.

Akaike Information Criterion (AIC):
- Akaike’s Information Criterion (AIC) estimates the relative Kullback-Leibler (KL) distance of the likelihood function specified by a fitted candidate model, from the unknown true likelihood function that generated the data [ejbfwejf](https://honglangwang.wordpress.com/2014/12/04/degrees-of-freedom-and-information-criteria).
- Does not assumes you have the true model and just tries to find the best approximation to reality which is unkown and high dimensional.

Bayesian information criterion (BIC):
- BIC is an estimate of a function of the posterior probability of a model being true, under a certain Bayesian setup.
- Assumes you already have the true model and are comparing candidates to see which one is the true model.
- BIC penalizes model complexity more heavily

$AIC = -2 \ln(\text{likelihood}) + 2k$
$BIC = -2 \ln(\text{likelihood}) + k\ln(N)$
- $k$ represents the degrees of freedom of the model and $N$ is number of observations in the data
- **likelihood** is the likelihood $P(X \mid \theta)$ or the probability of having the observations you got given a specific probability distribution and its parameters $\theta$)