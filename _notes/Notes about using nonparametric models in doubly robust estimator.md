However, Kang & Schafer (2007) demonstrated via simulation that the usual doubly robust estimator can be severely biased when both models are misspecified, even if they are nearly correct, and that bias is especially problematic when some estimated propensity scores are close to zero, yielding very large weights. 


Thus, the asymptotic variance of the estimator for μ can be approximated by the usual empirical sandwich technique; see Stefanski & Boos (2002). The resulting estimator for variance will be consistent for the true sampling variance even if one or both of the propensity or outcome regression models is incorrectly specified.



If the propensity score model is correct, we expect that ∑ni=1Ri/π(Xi,γˆ)≈n. When the estimated propensities for some observations are close to zero, this quantity can be very different from n. We thus consider propensity models and estimators that impose the restriction that this quantity be equal to n; if the chosen model is misspecified, this restriction will drive estimated propensities away from zero. We thus propose an enhanced propensity score model, given by


$$\operatorname{pr}(R=1 \mid X)=\pi(X, \delta, \gamma)=1-\frac{\exp \left(\delta+\widetilde{X}^{T} \gamma\right)}{1+\exp \left(\widetilde{X}^{T} \gamma\right)}$$

where δ is a scalar parameter. If δ = 0, (17) reduces to a usual logistic regression model; otherwise, δ is an enhancement imposing the constraint ∑ni=1Ri/π(Xi,δˆ,γˆ)=n. This follows because the score for δ is n−∑ni=1Ri/π(Xi,δ,γ), so that if maximum likelihood is used to estimate (δ,γ T)T, the constraint is satisfied automatically. Because π(X, δ,γ) can take values outside (0, 1), we impose 0 < π(X, δ,γ) < 1 and implement maximum likelihood subject to this restriction, which can be carried out with standard optimization packages.

- Their model improves existing methods for when regression outcome model is mispecified, but other cases it just does the same


Confidence intervals based on sandwich standard errors based on the doubly robust estimators for the most part attain nominal coverage except when both models are misspecified in the Kang & Schafer scenario; those for μˆPROJ and μˆenPROJ perform consistently well except in this case.




When both models are correct and γ is estimated by maximum likelihood, all doubly robust estimators are consistent with the same asymptotic variance; moreover, the asymptotic properties do not depend on the method used to estimate β (Tan, 2007; Tsiatis & Davidian, 2007).





# Consequences of Using Advanced Data Adaptive Approaches
- if nuisance parameters are estimated using maximum likelihood, the resulting estimator of the parameter of interest is asymptotically linear even if one of the nuisance parameter models has been misspecified. 
- In contrast, when nuisance parameters are estimated using data-adaptive approaches, the implications of inconsistently estimating one nuisance parameter are much more serious. Generally, the resulting estimator is irregular, exhibits large bias and has a convergence rate slower than root-n⁠. As we show below, the implications for inference are dire: regardless of nominal level, the coverage of naïve two-sided confidence intervals tends to zero and the Type I error rate of two-sided hypothesis tests tends to unity as the sample size increases. 
- https://academic.oup.com/biomet/article/104/4/863/4554445#SEC5




# Van der Laan (2014) made a nonparametric approach for doubly robust estimator but apparently it's too complex to have been implemented
- of van der Laan (2014), who focused on the counterfactual mean under a single time-point intervention and considered targeted minimum loss-based estimation. As the average treatment effect is the difference between two counterfactual means under different treatments, it too was directly addressed. The estimators proposed therein were shown to be doubly robust with respect to not only consistency but also asymptotic linearity. 


- Complicated ensemble estimators involve optimal trade-off of bias and variance w.r.t. the infinite dimensional nuisance parameter itself, they result in a sub-optimal bias/variance trade-off for the resulting real-valued estimator of the estimand.
- We demonstrate that additional targeting of the estimators of these nuisance parameters guarantees that this bias for the estimand is second order and thereby allows us to prove theorems that establish asymptotic linearity of the estimator of the treatment specific mean under regularity conditions. These insights result in novel targeted minimum loss-based estimators (TMLEs) that use ensemble learning with additional targeted bias reduction to construct estimators of the nuisance parameters.



# Causal Inference Class Notes
There are two reasons for doing sample splitting: the first is that the analysis
is more straightforward, and the second more important reason is that it prevents
overfitting and allows for the use of arbitrarily complex estimators µba (e.g., random
forests, boosting, neural nets). Without sample splitting, one would have to restrict
the complexity of the estimator µba via empirical process conditions (e.g., via Donsker
class or entropy restrictions). Intuitively, this is because the estimator ψb is using the
data twice: once to estimate the unknown function µa and once to estimate the bias
correction. Sample splitting ensures that these tasks are accomplished independently.