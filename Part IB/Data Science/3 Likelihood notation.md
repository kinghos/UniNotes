Likelihood is denoted as $\text{Pr}_{X}(x)$ and defined as
$$\text{Pr}_{X}(x)=\begin{cases}
\mathbb{P}(X=x) & \text{where $X$ is discrete} \\
\text{pdf}(x) & \text{where $X$ is continuous}
\end{cases}$$
For parameterised random variables, write $\text{Pr}_{X}(x;\theta)$

#### Joint likelihoods
$\text{Pr}_{X,Y}(x,y)$ is called the joint likelihood of $X$ and $Y$
For independent random variables,
$$
\text{Pr}_{X,Y}(x,y)=\text{Pr}_{X}(x)\text{Pr}_{Y}(y)
$$
Independently identically-distributed (IID) sample from $X$:
$$
\text{Pr}(x_{1},\dots,x_{n})=\text{Pr}_{X}(x_{1})\times\dots \times  \text{Pr}_{X}(x_{n})
$$
#### Maximum Likelihood Estimation


