Given a dataset of numerical values $[x_{1},x_{2},\dots,x_{n}]$, the empirical cumulative distribution or ECDF is
$$
\hat{F}(x)=\frac{1}{n}(\text{how many datapoints} \leq x)
$$
#### The empirical distribution
Given a dataset $[x_{1},x_{2},\dots,x_{n}]$ let $\hat{X}$ be the random variable obtained by picking one of the $x_{i}$ at random. This satisfies the law of total probability. We say this random variable has the empirical distribution of the dataset.
This applies to any type of data, where as the ECDF only applies to real-valued random variables

#### Inference/generalisation
Given a dataset x,
1. Decide on a readout function $t(x)$
2. Simulate a multiverse of datasets
	- Fit a model for the dataset
	- Let $X^*$ be a random synthetic dataset, generated from the fitted model
	- Simulate many synthetic datasets
3. Compute $t$ for each dataset, and report the spread of $t$
