---
title: How does Quadratic Voting Work
tree_state: 🌱
---

Quadratic voting can alleviate a lot of the problems that ranked choice voting systems (like some of the ones I explained in [[How Not to be Wrong Excerpt Public Opinion Doesn't Exist]]) suffer from. This is because all ranked choice voting systems inherently cannot be optimal due to Arrow's impossibility theorem.

How does Quadratic voting work:
https://vitalik.ca/general/2019/12/07/quadratic.html

If you use quadratic voting for a 3 candidate election, then for each candidate you could spend tokens to vote either for or against them. Then you could have something like the following situation.

> **The intuitive argument for those interested**: suppose there are established candidates A and B and new candidate C. Some people favor C > A > B but others C > B > A. in a regular vote, if both sides think C stands no chance, they decide may as well vote their preference between A and B, so C gets no votes, and C's failure becomes a self-fulfilling prophecy. In quadratic voting the former group would vote [A +10, B -10, C +1] and the latter [A -10, B +10, C +1], so the A and B votes cancel out and C's popularity shines through.