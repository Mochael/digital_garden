---
title: Intuition Behind the Doubly Robust Estimator
tree_state: 🌱
---

## The Inverse Probability Weighted Estimator
- Rebalancing data is necessary so that we aren't dominated by outcomes under treatment/nontreatment which could inflate/deflate treatment effect
$$\widehat{\Delta}_{I P W}=\frac{1}{n} \sum_{i=1}^{n}[\frac{A_{i} Y_{i}}{\pi(\mathbf{X}_{i} ; \widehat{\gamma})}-\frac{(1-A_{i}) Y_{i}}{1-\pi(\mathbf{X}_{i} ; \widehat{\gamma})}]$$

## Doubly Robust Estimator
$$\begin{aligned}
\widehat{\Delta}_{D R}=\frac{1}{n} \sum_{i=1}^{n}\left[\frac{A_{i} Y_{i}}{\pi\left(\mathbf{X}_{i} ; \widehat{\gamma}\right)}-\frac{\left(1-A_{i}\right) Y_{i}}{1-\pi\left(\mathbf{X}_{i} ; \widehat{\gamma}\right)}-\left[\frac{A_{i}-\pi\left(\mathbf{X}_{i} ; \widehat{\gamma}\right)}{\pi\left(\mathbf{X}_{i} ; \widehat{\gamma}\right)}\right] \mu\left(1, \mathbf{X}_{i} ; \widehat{\alpha}\right)\right.
-&\left.\left[\frac{A_{i}-\pi\left(\mathbf{X}_{i} ; \widehat{\gamma}\right)}{1-\pi\left(\mathbf{X}_{i} ; \widehat{\gamma}\right)}\right] \mu\left(0, \mathbf{X}_{i} ; \widehat{\alpha}\right)\right]
\end{aligned}$$


## When Treatment = 1
$$\tau_{i}^{D R}=\left[\left[\frac{Y_{i}^{1}}{e\left(\mathbf{X}_{\mathbf{i}}, \hat{\beta}_{i}\right)}-\frac{\left(1-e\left(\mathbf{X}_{\mathbf{i}}, \hat{\beta}_{i}\right)\right)}{e\left(\mathbf{X}_{\mathbf{i}}, \hat{\beta}_{i}\right)} m_{1}\left(\mathbf{X}_{\mathbf{i}}, \hat{\alpha}_{1}\right)\right]-\left[m_{0}\left(\mathbf{X}_{\mathbf{i}}, \hat{\alpha}_{0}\right)\right]\right]$$

$$ = \left[\left[f_{1}\left(\mathbf{X}_{\mathbf{i}}, \hat{\alpha_{1}}\right)-f_{0}\left(\mathbf{X}_{\mathbf{i}}, \hat{\alpha_{0}}\right)\right]+\frac{Y_{i}^{1}-f_{1}\left(\mathbf{X}_{\mathbf{i}}, \hat{\alpha_{1}}\right)}{p\left(\mathbf{X}_{\mathbf{i}}, \hat{\beta}_{i}\right)}\right]
$$

$$ = f_{1}-f_{0}-\frac{Y_0-f_{0}}{1-p}$$

- Left side of equation $m_1-m_0$ is the treatment effect based on your expected values
- Right side of equation weights the prior information of the true outcome $Y_i$, so that if $Y_i$ is lower than expected outcome, the estimation will be lowered (and if $Y_i$ is higher than expected then the estimated effect will be increased)
	- This adjustment is scaled by the propensity score. So if we notice that data points with one specific configuration of covariates are barely ever treated (i.e. low propensity score), then the $\frac{Y_{i}^{1}-m_{1}\left(\mathbf{X}_{\mathbf{i}}, \hat{\alpha_{1}}\right)}{e\left(\mathbf{X}_{\mathbf{i}}, \hat{\beta}_{i}\right)}$ will be larger so now the $m_1$ model will have less weight and the actual outcome $Y_1$ will have more impact on the anticipated treatment effect for datapoints with those covariates.


## When Treatment = 0
$$\tau_{i}^{D R}=\left[m_{1}\left(\mathbf{X}_{\mathbf{i}}, \hat{\alpha}_{1}\right)\right] - \left[\left[\frac{Y_{i}^{0} +  m_{0}\left(\mathbf{X}_{\mathbf{i}}, \hat{\alpha_{0}}\right) (1-e\left(\mathbf{X}_{\mathbf{i}}, \hat{\beta}_{i}\right)) - m_{0}\left(\mathbf{X}_{\mathbf{i}}, \hat{\alpha_{0}}\right)}{1 - e\left(\mathbf{X}_{\mathbf{i}}, \hat{\beta}_{i}\right)}\right]\right]$$

$$= \left[\left[f_{1}\left(\mathbf{X}_{\mathbf{i}}, \hat{\alpha_{1}}\right)-f_{0}\left(\mathbf{X}_{\mathbf{i}}, \hat{\alpha_{0}}\right)\right]-\frac{Y_{i}^{0}-f_{0}\left(\mathbf{X}_{\mathbf{i}}, \hat{\alpha_{0}}\right)}{ 1 - p\left(\mathbf{X}_{\mathbf{i}}, \hat{\beta}_{i}\right)}\right]$$
- Imagine that we have a covariate such that high values of the covariate are almost always treated, but datapoints with high values of the covariate always (for both treated and non-treated groups) have a high value in the outcome variable. If we were to use just the $m_1$ and $m_0$ models for estimating ITE, then since we hardly observe any $m_0$ values with a high value of this covariate, then for a datapoint with the high value that is not treated, we would likely overweight the treatment effect for this datapoint. However, since we include the outcome from the actual datapoint, $Y^0$, and we weight it's influence by the propensity (which will make the observed outcome have a larger influence in this situation) we can accurately estimate that the treatment effect for this datapoint won't actually be that high. Therefore, this demonstrates how the doubly robust estimator can handle measured confounders just the feature in this example.



 Imagine that we have a feature with the following properties:
 - high values of the covariate are almost always treated
 - datapoints with high values of the covariate always (for both treated and non-treated groups) have high values in the outcome variable. 
 - the covariate has no effect on the treatment effect
 
 - If we were to use just the $f_1$ and $f_0$ models (i.e. the t-learner) for estimating the ITEs, then we would likely pick this feature out as a useful predictor for high values in the $f_1$ model. Whereas in the $f_0$ model, this feature probably wouldn't even be used since we don't observe many datapoints with high values that are untreated. Therefore, this feature would be deemed to have a signficiant influence on the treatment effect using the t-learner estimator.
 - If we use the dr_tau estimator then we weight the influence of this feature by the propensity to be treated for those with specific values of this feature. Suppose we have a nontreated datapoint Therefore, since the probability to be treated is low for datapoints with we would discount the influence from the $f_0$ and $f_1$ model
 we would likely overweight the treatment effect for this datapoint. However, since we include the outcome from the actual datapoint, $Y^0$, and we weight it's influence by the propensity (which will make the observed outcome have a larger influence in this situation) we can accurately estimate that the treatment effect for this datapoint won't actually be that high. Therefore, this demonstrates how the doubly robust estimator can handle measured confounders just the feature in this example.
 
 
 # IMPORTANT TAKEWAY
 - actually if we use this, then the treated values would have a high ITE, but the untreated values would have a low ITE
	 - in this case then it would be more useful to do matching to nontreated and treated units 
	 - maybe we should only consider datapoints where nontreated and treated datapoints with the feature have high ITE

## Interesting alternative perspective on propensity and regression
http://www.amitsharma.in/post/doubly-robust-estimation-a-simple-guide/
> With messy data from the real-world, it is anybody's guess whether the data is missing at random, or what the correct probabilities of omission are.