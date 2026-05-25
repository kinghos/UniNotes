Continuous variables are defined with **probability density functions (PDFs)**
$$
P[a\leq X\leq b]=\int^b_{a}f(x)\, dx
$$
$f(a)$ is probability density
The cumulative distribution function is computed by
$$F_{X}(a)=\int^a_{-\infty}f(x)\,dx$$
$$E[X]=\int^\infty_{-\infty}xf(x)\,dx$$
$$E[g(x)]=\int^\infty_{-\infty}g(x)f(x)\,dx$$
#### Uniform 
$X \sim \text{Uni}(\alpha,\beta)$
PDF is $\frac{1}{\beta-\alpha}$
$E[X]=\frac{{~a+\beta}}{2}$

#### Exponential
$X\sim \text{Exp}(\lambda)$
PDF is $\lambda e^{-\lambda x}$
$E[X]=\frac{1}{\lambda}, V[X]=\frac{1}{\lambda^2}$

#### Normal
$X\sim \mathcal{N}(\mu,\sigma^2)$
PDF is $\frac{1}{\sigma \sqrt{ 2\pi }}e^{-(x-\mu)^2/2\sigma^2}$


$$\begin{align}

F_T(t) &= P\left( \frac{X}{Y}\leq t \right)\\
&=\int^0_{-\infty}P\left( \frac{X}{Y}\leq t\mid Y=y \right)\phi(y)\,dy+\int^\infty_{0}P\left( \frac{X}{Y}\geq t\mid Y=y \right)\phi(y)\,dy \\
&=\int^0_{-\infty}P\left( \frac{X}{y}\leq t \right)\phi(y)\,dy+\int^\infty_{0}P\left( \frac{X}{y}\geq t \right)\phi(y)\,dy \\
&=\int^0_{-\infty}P(X\leq yt)\phi(y)\,dy + \int^\infty_{0}P(X\geq yt)\phi(y)\,dy \\
&=\int^0_{-\infty}(1-\Phi(yt))\phi(y)\,dy + \int^\infty_{0}\Phi(yt)\phi(y)\,dy \\
&= \int^0_{-\infty}\Phi(-yt)\phi(y)\,dy+\int^\infty_{0}\Phi(yt)\phi(y)\,dy \\
u&=-y,dy=-du \\
&=2\int ^\infty_{0}\phi
\end{align}$$