#### Estimating population size
- Suppose you take a sample from the discrete uniform distribution over $[1,N]$, without replacement
- Construct an unbiased estimator $T_{1}$ using the sample mean
$$\overline{X}_{n}=\frac{{X_{1}+X_{2}+\dots+X_{n}}}{n}$$
- Linearity of expectation applies
$$\begin{align}
E[\overline{X}_{n}]&=\frac{n\cdot E[X_{1}]}{n}=E[X_{1}] \\
&=\sum^N_{i=1}i\cdot \frac{1}{N}=\frac{{N+1}}{2}
\end{align} $$
Thus $T_{1}:=2\overline{X}_{n}-1$

This estimator will often underestimate N. Finding an estimator which returns a value at least as big as the maximum value of $X_i$
