---
title: EconML Metalearners
tree_state: 🌱
---

Econml documentation lives here: https://econml.azurewebsites.net/

X LEARNER
$$
\hat{\mu}_0 = M_1(Y^0 \sim X^0) \\
\hat{\mu}_1 = M_2(Y^1 \sim X^1) \\
\hat{D}^1 = Y^1 - \hat{\mu}_0(X^1) \\
\hat{D}^0 = \hat{\mu}_1(X^0) - Y^0 \\
\hat{\tau}_0 = M_3(\hat{D}^0 \sim X^0) \\
\hat{\tau}_1 = M_4(\hat{D}^1 \sim X^1) \\
\hat{\tau} = g(x)\hat{\tau}_0(x) + (1-g(x))  \hat{\tau}_1(x)
$$

DA LEARNER
$$
\hat{\mu}_0 = M_1\left(Y^0 \sim X^0, \text{weights}=\frac{g(X^0)}{1-g(X^0)}\right) \\
\hat{\mu}_1 = M_2\left(Y^1 \sim X^1, \text{weights}=\frac{1-g(X^1)}{g(X^1)}\right) \\
\hat{D}^1 = Y^1 - \hat{\mu}_0(X^1) \\
\hat{D}^0 = \hat{\mu}_1(X^0) - Y^0 \\
\hat{\tau} = M_3(\hat{D}^0|\hat{D}^1 \sim X^0|X^1)
$$

