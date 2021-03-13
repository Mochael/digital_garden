---
title: What is the Negative Binomial Distribution
tree_state: 🌱
---

- Let's define $Y$ as the number of failures before the $r$th success.
- We will assume that every individual trial is an independent bernoulli event with probability of success $p$
- Then the probability of getting $Y$ failures before the $r$th success follows the negative binomial distribution which is:

$$P(Y=y \mid r, p)=\left(\begin{array}{c}r+y-1 \\ y\end{array}\right) p^{r}(1-p)^{y}, \quad y=0,1, \ldots$$

###  Dissecting this equation:
Example 1: Consider the case where we want to know the probability of getting 10 failures, before getting the first success.
- In this case, the only way we could get 10 failures before the first success is for the first 10 trials to be failures, and then the last trial to be a success. Looking at the equation for the negative binomial, we would have $P(Y=10 \mid r=1, p)=\left(\begin{array}{c}1+10-1 \\ 10 \end{array}\right) p^{1}(1-p)^{10} = p^{1}(1-p)^{10}$. We completely remove the $\left(\begin{array}{c}r+y-1 \\ y\end{array}\right)$ term because there is only 1 way to pick 

Now thinking about this $\left(\begin{array}{c}r+y-1 \\ y\end{array}\right)$ term, this is equivalent to saying: how many ways can we can select $y$ failures from $r+y-1$ different trials.
- There are in total $r+y$ ($r$ successes and $y$ failures), but we know that the last trial must always be a success, because we are considering the probability of $Y$ failures before **before** the $r$th success. So we shouldn't even consider cases where we get $r$ successes before we $y$ failures. Therefore, we must fix the last trial to be a success and thus we are left with selecting $y$ successes from $r+y-1$ trials.

The  $p^{r}(1-p)^{y}$ term is just expressing the probability of getting $r$ successes and $y$ failures when probability of success is $p$ and probability of failure is $1-p$ (just like in the binomial distribution or the bernoulli likelihood).
- The probability of getting that $y$ successes and $r$ failures remains the same across any orderings of successes and failures since each trial is independent and therefore changes in results from trials don't influence one another. This is why the $p^{r}(1-p)^{y}$ does not change for reordering of the failures (from the $\left(\begin{array}{c}r+y-1 \\ y\end{array}\right)$ term).