Expectations preserve linearity: if $a$ and $b$ are constants, then 
$$E[aX+b]=aE[X]+b$$
Additivity:
$$E[X +Y] = E[X] + E[Y]$$
#### LOTUS
Law of the unconscious statistician
Let $X$ be a random variable, and $Y$ another random variable that is a function of $X$, so $Y=g(x)$. Let $p(x)$ be a PMF of $X$. Then
$$E[Y]=E[g(x)]=\sum_{x:p(x)>0}g(x)p(x)$$
This avoids needing to know the PMF of $Y$.
Also known as the **expected value of a function of a random variable**
If $X$ is a discrete random variable, then
$E[X^n]$ is known as the $n$th moment of X
#### Variance
Variance is a measure of spread
$$\begin{align}
V[X]&=E[(X-\mu)^2] \\
&= E[X^2]-(E[X])^2
\end{align}$$
#### Standard deviation
Standard deviation is a kind of average distance of a sample of the mean, i.e. a root mean square average
$$SD[X]=\sqrt{ V[X] }$$
Variance is NOT linear
$$V[aX+b]=a^2V[X]$$

#### Bernoulli
A Bernoulli RV $X$ maps success of an experiment to 1 and failure to 0.
$$X\sim \text{Ber}(p)$$
Range is $\{ 0,1 \}$, where $p$ is the probability of 1.
$E[V]=p, V[X]=p(1-p)$

#### Binomial
$$X\sim\text{Bin}(n, p)$$
$E[X]=np, V[X]=np(1-p)$
$$P[X=k]=p(k)={n\choose k} p^k(1-p)^{n-k}$$
Binomial RV is the sum of n independent Bernoulli RVs