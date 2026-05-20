#### Markov's Inequality
For any non-negative random variable $X$ with finite $E[X]$, it holds for any $a>0$,
$$P[X\geq a]\leq \frac{E[X]}{a}$$
Tail-bound - it upper bounds the probability that the random variable exceeds its mean
Alternatively
$$P[X\geq \delta \cdot E[X]]\leq \frac{1}{\delta}$$
Bounds for $\leq$ can be found by declaring a new variable $Y=a-X$

#### Chebyshev's Inequality
For any random variable $X$ with finite $E[X]$ and $V[X]$, for any $a>0$,
$$P[|X-E[X]|\geq a]\leq \frac{V[X]}{a^2}$$
or equivalently
$$P[|X-E[X]]|\geq \sqrt{ \delta \cdot V[X] }\leq \frac{1}{\delta}$$
Unlike Markov, this is two-sided and holds for random variables with negative values, and yields stronger bounds
This is also known as the Second Moment Method
