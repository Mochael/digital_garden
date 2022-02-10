---
title: Interesting Causal Inference Papers
tree_state: 🌱
---


Andrew Ng on largest impact patients aren't the riskiest: https://www.ahajournals.org/doi/pdf/10.1161/CIRCOUTCOMES.118.005010

What is the c-statistic for benefit: https://pubmed.ncbi.nlm.nih.gov/29132832/

Neural networks for estimating treatment effects: https://arxiv.org/pdf/1906.02120.pdf

[Representation Learning for Treatment Effect Estimation from Observational Data](https://github.com/Osier-Yi/SITE) Paper that we are comparing our models to

[Counterfactual regression (CFR) by learning balanced representations](https://github.com/clinicalml/cfrnet) current state of the art for 

- Our second contribution is to excplicitly account and adjust for the bias induced by treatment group imbalance. To this end, we seek a representation Φ and hypothesis h that minimizes a trade-off between predictive accuracy and imbalance in the representation space

[Causal Random Forests](https://www.tandfonline.com/doi/full/10.1080/01621459.2017.1319839) they recommend splitting the training set into 2 separate sets: 1 to determine the splits in each tree and 1 to determine outcome predictions at each split

https://scholar.princeton.edu/sites/default/files/bstewart/files/lundberg_methods_tutorial_reading_group_version.pdf slideshow about using causal forests

https://github.com/grf-labs/grf r package for implementing causal forests (causal forests aren't in python yet I don't think)

CEVAE original paper (Louizos et al. [2017](https://bookdown.org/phamtrongthang123/notebookCEVAE/#ref-louizos2017causal)).

- does not handle selection bias (seems to be the case when covariate X influences treatment instead of only a confounding variable influencing it)
- https://bookdown.org/phamtrongthang123/notebookCEVAE/exp.html#benchmark-dataset simplified explanation in a notebook (but there may be some errors in explanation)

Read into implementing Van Der Laan 2014 (if I still need to do this if we are using cross fitting: we may not use cross fitting so this could be very useful) https://www.degruyter.com/view/journals/ijb/10/1/article-p29.xml?language=en

1. Basically if you use complicated estimators for nuisance functions it seems that you need to use either cross validation, or some different formulation of the dr_estimator so that your results aren't awful if your nuisance function is misspecified 
2. https://core.ac.uk/download/pdf/61322814.pdf this paper is about how using data apative things in doubly robust doesn't immediately extend to inference
3. https://academic.oup.com/biomet/article/104/4/863/4554445 this paper is very interesting and talks about how well our confidence intervals and inference hold up when complicated estimators are misspecified and how to fix this

Identifying Positivity Violations: https://pubmed.ncbi.nlm.nih.gov/21030422/

The method from the https://github.com/usaito/counterfactual-cv paper uses something to regularize distance between $\mu_1$ and $\mu_0$, so I should look into what that is doing and write about it

1. They are saying that ranking correlation between MSE(their tau, econML model) and  MSE(true tau, econML model) is very high

Test out different models of true ITE/CATE:

1. > Several prior studies tackle the model evaluation problem in CATE prediction. (Gutierrez & Gerardy ´ , 2017) proposed using the inverse probability weighting (IPW) outcome as the pseudo-label for the true CATE for the calculation of an evaluation metric. (Schuler et al., 2018) used the loss function of R-learner (Nie & Wager, 2017) for the evaluation. (Alaa & Van Der Schaar, 2019) used influence functions to obtain a more efficient estimator for the loss. These works are mainly focused on improving the accuracy of estimating the evaluation metric of interest. [Representation Learning for Treatment Effect Estimation from Observational Data](https://github.com/Osier-Yi/SITE)

   1. In this paper they focus on measuring ranking (spearman correlation) instead of also measuring MSE and pearson correlation

2. Inverse Probability Weighted (IPW): $\widehat{\psi}_{i p w}=\mathbb{P}_{n}\left[\left\{\frac{A}{\widehat{\pi}(X)}-\frac{1-A}{1-\widehat{\pi}(X)}\right\} Y\right]$

3. Using the loss function of R-learner (Nie & Wager, 2017) for the evaluation

4. Using influence functions to obtain a more efficient estimator for the loss