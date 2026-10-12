#### Maximum Likelihood Estimation
- Models typically has unknown parameters
- Estimate parameters using MLE
- The likelihood is the probability of seeing the data that we actually saw (dependent on the parameters)
- Pick parameters that maximise the likelihood

Based on an observation (e.g. flipping a coin 10 times and getting 6 heads), find the value of the parameters to the distribution that gives the largest value for that observation (the likelihood)
**Sanity check:** does the answer depend on the data supplied?

When there are many independent datapoints, the log-likelihood is useful as it turns products into sums.
$$\text{lik}(\text{data})=\prod^n_{i=1}\text{lik}(x_{i})$$
