#### Empirical Distribution Function
Let $X_{1},X_{2},\dots,X_{n}$ be samples and $F$ be the corresponding distribution function. For any $a \in \mathbb{R}$ define
$$F_{n}(a):=\frac{\text{number of }X_{i}\in(-\infty,a]}{n}$$
By the Law of Large Numbers, more samples means there is a more accurate estimation

#### Estimators
An estimate is a value $t$ that only depends on the dataset $x_{1},x_{2},\dots ,x_{n}$
$$t=h(x_{1},x_{2},\dots,x_{n})$$
Then $t$ is a realisation of the random variable
$$T=h(X_{1},X_{2},\dots,X_{n})$$
which is called an estimator

An estimator $T$ is called an unbiased estimator for the parameter $\theta$ if 
$$E[T]=\theta$$
irrespective of the value $\theta$
The bias is defined as 
$$E[T]-\theta=E[T-\theta]$$

#### Jensen's Inequality
For any random variable $X$ and any convex function $g: \mathbb{R}\to \mathbb{R}$, we have
$$E[g(X)]\geq g(E[X])$$
If g is strictly convex and $X$ is not constant, then the inequality is strict
