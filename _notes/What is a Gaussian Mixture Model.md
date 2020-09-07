---
title: What is a Gaussian Mixture Model
tree_state: 🌱
---

The Gaussian Mixture Model (GMM) is a probabilistic model that assumes all the data points are generated from a mixture of a finite number of Gaussian distributions with unknown parameters.

We can look at a GMM as assuming the observed data points come from the following probability density function (pdf):
$$p(x) = \sum_{k=1}^K w_k N(x \mid \mu_k, \Sigma_k)$$

- This pdf indicates that we have a probability of $w_k$ of selecting the $k$th Gaussian for generating the observed data $x$.

This model is used as a clustering algorithm to figure out which datapoints came from which Gaussian distribution. GMM can be viewed as an extension of the K-Means algorithm where in the K-Means algorithm we assume the Gaussians all have a covariance $\sigma^2 I$ and that $\sigma \rightarrow 0$, so we only need to estimate the means. We can solve for the parameters of the GMM with [[What is the EM Algorithm]].