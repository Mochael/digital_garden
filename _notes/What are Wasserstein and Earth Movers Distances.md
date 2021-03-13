---
title: What are Wasserstein and Earth Movers Distances
tree_state: 🌱
---
## What is Wasserstein distance


$\operatorname{Let}(\mathcal{X}, d)$ be a Polish metric space, and let $p \in[1, \infty) .$ For any two probability measures $\mu, \nu$ on $\mathcal{X},$ the Wasserstein distance of order $p$ between $\mu$ and $\nu$ is defined by the formula
$$
\begin{aligned}
W_{p}(\mu, \nu) &=\left(\inf _{\pi \in \Pi(\mu, \nu)} \int_{\mathcal{X}} d(x, y)^{p} d \pi(x, y)\right)^{1 / p} \\
&=\inf \left\{\left[\mathbb{E} d(X, Y)^{p}\right]^{\frac{1}{p}}, \quad \operatorname{law}(X)=\mu, \quad \operatorname{law}(Y)=\nu\right\}
\end{aligned}
$$

$$W_{p}\left(\mu_{0}, \nu\right)=\inf \{\mathbb{E}\left[d\left(X_{0}, X_{1}\right)^{p}\right]^{1 / p} \mid X_{0} \text{ comes from } \mu \text{ and } X_{1} \text{ comes from } \nu \}$$


## What is the Earth Mover's Distance
Finally, the Earth Mover (EM) (version of Wasserstein distance): Let $\Pi\left(P_{r}, P_{g}\right)$ be the set of all joint distributions $\gamma$ whose marginal distributions are $P_{r}$ and $P_{g} .$ Then.
$$
W\left(P_{r}, P_{g}\right)=\inf _{\gamma \in \Pi\left(P_{r}, P_{g}\right)} \mathbb{E}_{(x, y) \sim \gamma}[\|x-y\|]
$$

First, the intuitive goal of the EM distance. Probability distributions are defined by how much mass they put on each point. Imagine we started with distribution $P_{r},$ and wanted to move mass around to change the distribution into $P_{g}$. Moving mass $m$ by distance $d$ costs $m \cdot d$ effort. The earth mover distance is the minimal effort we need to spend.
Why does the infimum over $\Pi\left(P_{r}, P_{g}\right)$ give the minimal effort? You can think of each $\gamma \in \Pi$ as a transport plan. To execute the plan, for all $x, y$ move $\gamma(x, y)$ mass from $x$ to $y$
Every strategy for moving weight can be represented this way. But what properties does the plan need to satisfy to transform $P_{r}$ into $P_{g} ?$
The amount of mass that leaves $x$ is $\int_{y} \gamma(x, y) d y .$ This must equal $P_{r}(x),$ the amount of mass originally at $x$.
The amount of mass that enters $y$ is $\int_{x} \gamma(x, y) d x .$ This must equal $P_{g}(y),$ the amount of mass that ends up at $y$.
This shows why the marginals of $\gamma \in \Pi$ must be $P_{r}$ and $P_{g}$. For scoring, the effort spent is $\int_{x} \int_{y} \gamma(x, y)\|x-y\| d y d x=\mathbb{E}_{(x, y) \sim \gamma}[\|x-y\|]$ Computing the infinum of this over all valid $\gamma$
gives the earth mover distance.


Check out [this link](https://www.alexirpan.com/2017/02/22/wasserstein-gan.html#aside-whats-up-with-the-earth-mover-definition:~:text=Aside%3A%20What%E2%80%99s%20Up%20With%20The%20Earth%20Mover%20Definition%3F) for a good explanation.