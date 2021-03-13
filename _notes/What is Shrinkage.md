---
title: What is Shrinkage
tree_state: 🌱
---

Overall, **shrinkage** in statistics refers to techniques to reduce the effects of sampling variation.

Examples:
- If we build a regression model on a training set, measure it's R2 on the training set, and then apply it to a new data set, the model will likely have lower R2 on the new data set. We can incorporate shrinkage by adding regularization to the model.
- Let's say you have a dataset that gives information on at bats in the MLB and you try and estimate each batter's RBI or something like that. Some batters have only batted twice, but others have batted 100 times. So, there will be a large impact from sampling variation in our estimate if we just emperically calculate the RBI. So, we can apply shrinkage and use a prior on batting rate that has more influence on batters with less data.