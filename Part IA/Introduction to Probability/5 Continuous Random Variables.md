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


