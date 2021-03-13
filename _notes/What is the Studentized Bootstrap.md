---
title: What is the Studentized Bootstrap
tree_state: 🌱
---

Essentially it's where you perform nested iterations of bootstrapping. Repeat the following $b$ times:
1. Sample with replacement to get a new dataset. Treat this as your original observed dataset. Calculate the statistic of interest for this dataset $\theta^{b}$
2. Perform normal bootstrapping using this sampled dataset. $\theta^{b,1},...,\theta^{b,m}$
3. Collect the standard deviation (which is std error in this case) of the statistic across the nested bootstrap for this iteration, so the standard deviation of $\theta^{b,1},...,\theta^{b,m}$. So we will have a standard error associated with each $\theta^{b}$.


In normal bootstrapping we aim to approximate $(\hat{\theta} − \theta)$ with $(\tilde{\theta}-\hat{\theta})$. In studentized bootstrapping we aim to approximate $(\hat{\theta} − \theta)/SE(\hat{\theta})$ with $(\tilde{\theta}-\hat{\theta})/SE(\tilde{\theta})$.

For more see:
https://www.stat.cmu.edu/~ryantibs/advmethods/notes/bootstrap.pdf