---
title: Multinomial to Binomial Stick Breaking Construction
tree_state: 🌱
---

$$
\begin{aligned}
\operatorname{mult}(\mathbf{x} \mid N, \mathbf{\pi}) &=\prod_{k=1}^{K-1} \operatorname{binom}\left(x_{k} \mid N_{k}, \tilde{\pi}_{k}\right) \\
N_{k} &=N-\sum_{j<k} x_{j}, \quad \tilde{\pi}_{k}=\frac{\pi_{k}}{1-\sum_{j<k} \pi_{j}}, \quad k=2,3, \ldots, K \\
N_{1} &=N, \quad \tilde{\pi}_{1}=\pi_{1}
\end{aligned}
$$

$$
\begin{aligned}
\operatorname{mult}(\mathbf{x} \mid N, \bf{\pi}) &=\frac{N !}{x_{1} ! x_{2} ! \ldots x_{K} !} \pi_{1}^{x_{1}} \pi_{2}^{x_{2}} \cdots \pi_{K}^{x_{K}} \\
\operatorname{binom}\left(x_{k} \mid N_{k}, \tilde{\pi}_{k}\right) &=\left(\begin{array}{c}
N_{k} \\
x_{k}
\end{array}\right) \tilde{\pi}_{k}^{x_{k}}\left(1-\tilde{\pi}_{k}\right)^{N_{k}-x_{k}}
\end{aligned}
$$

- The first $\tilde \pi_1$ and $N_1$ will just take the form of the binomial distribution for $x_1$ successes (and $N-x_1$ failures).
- The second $\tilde \pi_2 = \frac{\pi_2}{1-\pi_1}$ and $N_2 = N - x_1$. $\tilde \pi_2 > \pi_2$ and $N_2 < N_1$. 
  - I interpret this as the probability of having the remaining $x_2$ successes out of the $N-N_1$ trials after removing the 1st side of the $k$ sided dice so we now have $k-1$ sides. There will be a higher probability of success for each trial since we already considered the success of the events for $x_1$, so it will not be in the set of failures (which this is also why we remove the events from $N_1$).
- If we repeat this in our product for each $K-1$, each subsequent $\tilde \pi_j$ will become a larger and larger proportion of the remaining probability $1-\sum_{j<k} \pi_{j}$ while $N_j$ keeps becoming smaller and smaller.



Proofs are here:

- https://gregorygundersen.com/blog/2020/07/01/multinomial-binomial/#linderman2015dependent