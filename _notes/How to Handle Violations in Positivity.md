How to Handle Violations in Positivity

https://academic.oup.com/aje/article/171/6/674/113230
Once detected, the epidemiologist can deal with violations of positivity in several ways. The simplest solution is restriction. While easy and effective, restriction has the effect of altering the target population for inference. This method is the one implicitly favored by epidemiologists using propensity scores, who match or “trim” their data to avoid regions of propensity score nonoverlap. Another approach, one that is most appropriate for random violations of positivity that are surrounded by regions in which positivity holds, is to interpolate to areas of nonpositivity.

If we find covariate values where posivity is violated then:
1.  For variables V that are not confounders, one should look to the literature on exposure opportunity
2.  For confounders that are not time-varying, the best method for dealing with nonpositivity depends on the circumstances. If the nonpositivity is both random and internal (e.g., positivity at ages 36–40 and 46–50 years but not at ages 41–45 years), cautious interpolation or smoothing over the region of nonpositivity is reasonable. In such cases, restriction may prove more difficult, not least due to clearly defining the altered estimand. If the nonpositivity is random and external (e.g., no positivity under age 36 years), extrapolation is possible but often ill-advised. In such cases, restricting inference to persons aged 36 years or more may be a prudent approach. If the nonpositivity is deterministic, however, restriction can be recommended as an appropriate approach in many cases.
3.  Lastly, nonpositivity by a time-varying confounder poses an analytic challenge. In such cases, g-estimation of a structural nested model (11) or g-computation (12) may be a way forward, but more research is needed.


https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4107929/
In summary, we offer the following advice for applied analyses: First, define the causal effect of interest based on careful consideration of structural positivity violations. Second, consider estimator behaviour in the context of positivity violations when selecting an estimator. Third, apply the parametric bootstrap provide a quantitative measure of estimator bias under data simulated to approximate the true data generating distribution. Finally, when positivity violations are a concern, choose an estimator that selects systematically among a family of parameters based on the trade-off between data support and proximity to the initial target of inference.

Basically here is what they propose:
1. Create doubly robust estimator for the effect you're interested in and estimate that effect for the data
2. use the nuisance functions you generated for this estimator to then simulate new data via bootstrapping
3. use different versions of estimators with varied positivity enforcement strength (i.e. leave all data as is, remove occastional points that violate positivty, remove all possible datapoints and features with violated positivity)
4. Calculate how the bias between the bootstrapped estimated treatment effects and the original one you calculated (average of bootstrapped effects - original effect)
5. Pick the version of the estimator that fits your tolerance between trading off between posivity violation and model bias 