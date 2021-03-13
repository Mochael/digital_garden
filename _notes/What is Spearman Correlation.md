---
title: What is Spearman Correlation
tree_state: 🌱
---

Suppose we have two random variables $X$ and $Y$ with $n$ paired samples from their joint distribution. We can define the ranking, $\mathrm{rg}_{X}$, of the variable $X$ for $X_1,...,X_n$ to be the position of each $X_i$ when $X_1,...,X_n$ are ordered from least to greatest. For example, suppose we have $(X_1,X_2,X_3,X_4) = (7,9.3,2,-1)$, then the least to greatest ordering of $X$ is $(-1,2,7,9.3)$ and $\mathrm{rg}_{X} = (4, 3, 1, 2)$.

The Spearman correlation $r_{s}$ is then the same thing as the Pearson correlation coefficient between the rank variables:
$$r_{s}=\rho_{\mathrm{rg}_{X}, \mathrm{rg}_{Y}}=\frac{\operatorname{cov}\left(\mathrm{rg}_{X}, \mathrm{rg}_{Y}\right)}{\sigma_{\mathrm{rg}_{X}} \sigma_{\mathrm{rg}_{Y}}}$$