#### Computational methods
Chance of hitting a mystery object A
$$
\mathbb{P}(X\in A)\approx \frac{1}{n}\sum^n_{i=1}\mathbf{1}_{x_{i}\in A}
$$
[[3 Expectation and variance#LOTUS|LOTUS]]
Monte Carlo integration:
$$
\mathbb{E}h(X)=\frac{1}{n}\sum^n_{i=1}h(x_{i})
$$
based on a sample of $x_{i}$s from $X$
Alternatively:
$$
\int^b_{x=a}h(x)\,dx\approx \sum^n_{i=1}h(x_{i}) \frac{{b-a}}{n})
$$
where $x_i$ is the midpoint of interval $i$
Recall the [[9 Bayesianism cont.|Bayesian update]] procedure:
$\text{Pr}_{\Theta}(\theta)+x\to\text{Pr}_{\Theta}(\theta\mid X=1)\propto\text{Pr}_{\Theta}(\theta)\text{Pr}_{X}(x\mid\the)$