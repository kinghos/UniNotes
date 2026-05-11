#### Poisson
Poisson distribution is a binomial distribution with a given mean (rate) $\lambda=np$ and $\lim_{ n \to \infty }$. It is considered to approximate Binomial when $n$ is large and $p$ is small.
Its PMF is
$$P[X=k]=\frac{\lambda^k}{k!}e^{-\lambda}$$
$V[X]=\lambda,E[X]=\lambda$
A Poisson process is a model for a series of discrete events where the average time between events is known, but the exact timing of events is random

#### Geometric
$X$ is the number of independent Bernoulli trials until the first success, where $p$ is the probability of success
Its PMF is $$
P[X=n]=(1-p)^{n-1}p
$$
$V[X]=\frac{1-p}{p^2},E[X]=\frac{1}{p}$

#### Negative Binomial
$X$ is the number of independent Bernoulli trials until r successes and $p$ is the probability of a success.
Its PMF is $$P[X=n]={{n-1}\choose{r-1}}(1-p)^{n-r}p^r$$
$V[X]=\frac{r(1-p)}{p^2}, E[X]=\frac{r}{p}$
