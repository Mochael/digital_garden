---
title: What is the EM Algorithm
tree_state: 🌱
---

When we are given data, but we don't know the true underlying labels of the data, we can use the unsupervised EM algorithm to identify them.
- E-Step is essentially guessing labels using existing parameters
- M-Step is solving for new parameter values using the guessed labels

## **E Step**

- **Compute the expected value of the sufficient statistics of the hidden variables given current estimations of the model parameters.**
- **In K-Means, it's where each datapoint is assigned to the closest cluster (think of this as the cluster centers are latent random variables because a point's assignment in a Gaussian Mixture Model follows a probability distribution).**
- **We close the gap, making the lower bound=likelihood.**

## **M Step**

- **Compute the parameters under current results of the expected value of the hidden variables.**
- **We optimize a lower bound on the likelihood.**
- **In K-Means, it's where the cluster centers are recomputed to minimize the distance for the expected cluster assignments found in the E step (think of this as a parameter, because cluster centers are fixed values and not random variables).**


