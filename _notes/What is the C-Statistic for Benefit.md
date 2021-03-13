---
title: What is the C-Statistic for Benefit
tree_state: 🌱
---

Given two randomly chosen pairs, pair A and pair B (pairs are matched such that one unit is treated and one is untreated). What is the probability that the pair with the greater treatment effect estimate, also has the greater difference between the treated-untreated outcomes.

https://www.coursera.org/lecture/ai-for-medical-treatment/c-for-benefit-PDQQa

1. Get ITEs for each patient
2. Match each treated patient to an untreated patient by either their features or their ITE predictions (or both)
3. Calculate the observed benefit for each of the pairs as $Y_1-Y_0$, or the outcome for the treatment unit in the pair - the outcome of the nontreated unit in the pair.


Concordant pair:
- take 2 pairs and if the pair with the higher estimated effect actually has the higher outcome, then the two pairs are concordant
![Screen Shot 2021-03-11 at 2.09.31 PM.png](../search_pics/Screen%20Shot%202021-03-11%20at%202.09.31%20PM.png)

![Screen Shot 2021-03-11 at 2.11.06 PM.png](../search_pics/Screen%20Shot%202021-03-11%20at%202.11.06%20PM.png)

Ties:
![Screen Shot 2021-03-11 at 2.11.39 PM.png](../search_pics/Screen%20Shot%202021-03-11%20at%202.11.39%20PM.png)
![Screen Shot 2021-03-11 at 2.12.07 PM.png](../search_pics/Screen%20Shot%202021-03-11%20at%202.12.07%20PM.png)

Permissable Pairs:
- Pairs with different outcomes
![Screen Shot 2021-03-11 at 2.12.52 PM.png](../search_pics/Screen%20Shot%202021-03-11%20at%202.12.52%20PM.png)