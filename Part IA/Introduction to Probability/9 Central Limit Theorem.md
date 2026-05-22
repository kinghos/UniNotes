Let $X_{1},X_{2},\dots$ be any sequence of independently identically distributed random variables with finite expectation $\mu$ and finite variance $\sigma^2$. Let
$$Z_{n}:=\sqrt{ n }\cdot \frac{\overline{X}_{n}-\mu}{\sigma}=\frac{1}{\sqrt{ n }\cdot\sigma}\cdot \left( \sum^n_{i=1}X_{i}-n\mu \right)$$
Then for any number $a \in \mathbb{R}$ it holds that 
$$\lim_{ n \to \infty }F_{Z_{n}}(a)=\phi(a)=\frac{1}{\sqrt{ 2\pi }}\int^a_{-\infty}e^{-x^2/2}\,dx $$
where $\phi$ is the distribution function of the $\mathcal{N}(0,1)$ distribution
