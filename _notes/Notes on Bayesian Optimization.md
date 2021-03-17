---
title: Notes on Bayesian Optimization
tree_state: 🌱
---

- We assume smooth form of prior and then sample points to learn the posterior
  - Our goal is to find the optimal value of the posterior function while sampling from the posterior distribution as little as possible because sampling from the posterior is expensive
  - Basically we sample values from the posterior until we find the max and stop
    - We choose to sample the next point by trying to pick the area to sample from with the highest probability of having the max value
  - We do this to find the optimal hyperparameters by optimizing the cost function as a function of the hyperparameters
- Larger epsilon --> that you need a larger value of mu to beat that f+epsilon so therefore we would want to pick a spot with more variance so we have a larger change to be greater than
  - this is probably why we don't just pick an algorithm that will choose the largest value of mu, but instead we want the largest chance of getting a value higher than f+epsilon
  - Maximizing prob that mu > f+epsilon is the same as maximizing the probability that a random variable is lesss than mu - f + epsilon
  - *Expected Improvement* will be high when: i) the expected value of \mu_t(x) - f(x^+)*μ**t*(*x*)−*f*(*x*+) is high, or, ii) when the uncertainty \sigma_t(x)*σ**t*(*x*) around a point is high.
- We can sample from posterior distribution by sampling parameters from the prior distribution and generating a random value from the likelihood and this sampled prior
  - we then can accept the sample if it seems to have a high probability in the data
