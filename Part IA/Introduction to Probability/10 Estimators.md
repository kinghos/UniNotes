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
for all values of $\theta$
The bias is defined as 
$$E[T]-\theta=E[T-\theta]$$

#### Jensen's Inequality
For any random variable $X$ and any convex function $g: \mathbb{R}\to \mathbb{R}$, we have
$$E[g(X)]\geq g(E[X])$$
If g is strictly convex and $X$ is not constant, then the inequality is strict


#### Unbiased Estimators
$$\overline{X}_{n}:=X_{1}+X_{2}+\dots+X_{n}$$
$$S_{n}=S_{n}(X_{1},\dots,X_{n}):=\frac{1}{n-1}\sum^n_{i=1}(X_{i}-\overline{X}_{n})^2$$
Estimators for $\mu$ and $\sigma^2$ respectively
