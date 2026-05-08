A random variable $X$ is a function from the sample space to the real numbers. They are **not** events.
Events are conditions of a random variable.
The range of a variable is the values it can take with non-zero probability

#### Probability Mass Functions
A random variable $X$ is discrete if its range has countably many values
The PMF of a discrete random variable $X$ is a function $p(a)$ of $X$ that maps possible outcomes of a random variable to the corresponding probabilities:
$$p(a)=P[X=a]=p_{X}(a)$$
where probabilities sum to 1.

Let possible values of $X=\{ a_{1},a_{2},a_{3},\dots \}$
1. Axiom 1: $0\leq p(a_{i})\leq 1$
2. $p(a)=0$ if $a$ is not a possible value
3. By axiom 3: $\sum^\infty_{i=1}p(a_{i})=1$
4. Everything to do with discrete RVs is expressed as a sum
5. For continuous RVs, this is expressed as an integral

#### Cumulative Distribution Functions
The CDF of a random variable X is defined as 
$$F(a)=F_{X}(a)=P[X\leq a],-\infty<a<\infty$$
For a discrete variable $X$ the CDF is 
$$F(a)=P[X\leq a]=\sum_{\text{all }x\leq a}p(x)$$
1. $0\leq F(x)\leq{1}$ for all $x$
2. $\lim_{ x \to -\infty }F(x)=0$
3. $\lim_{ x \to \infty }F(x)=1$
4. $F(x)$ is a non-decreasing function of $x$

#### Expectation
Expectation of a discrete variable $X$ is defined as
$$E[X]=\sum_{x:P[x]>0}xP[x]$$
