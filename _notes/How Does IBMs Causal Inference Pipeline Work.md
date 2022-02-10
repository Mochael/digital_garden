---
title: How Does IBMs Causal Inference Pipeline Work
tree_state: 🌱
---

1. They take covariates from Linked Births and Infant Deaths Database and then run simulations to generate outcomes and treatments
	1. They ensure that their data does not have unmeasured confounding
2. In their pipeline they have the user input a causal graph which determines the relationships between covariates, treatment, factual outcome, and counterfactual outcome
	1. Allows for flexibility in how variables influence one another
3. They then generate a bunch of different datasets to evaluate model performance based on two different situations: performance based on sample size and performance based on the amount of missing outcomes
	1. They generate datasets $D_n$ where sample size $n \in \{1k, 2.5k, 5k, 10k, 25k, 50k \}$ for each dataset $D_i$
	2. They generate multiple (they don't specify) datasets with $n=10k$ where they decide to hide some of the outcomes
4. They then have a bunch of different error metrics that they use to compare true ITE/ATE to predicted ITE/ATE values and confidence intervals