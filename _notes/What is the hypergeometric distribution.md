---
title: What is the hypergeometric distribution
tree_state: 🌱
---

Suppose a population consists of $N$ items, $k$ of which are successes. And a random sample drawn from that population consists of $n$ items, $x$ of which are successes. Then the hypergeometric probability is:

{% raw %}
$$P(x \mid N, n, k) = \frac{{k \choose x} {N-k \choose n-x}}{{N \choose n}}$$
{% endraw %}

- The number of combinations between:
	- Ways to choose x successes from k successes
	- Ways to choose n-x successes from N-k successes
- Divided by number of ways to choose n samples from N total items