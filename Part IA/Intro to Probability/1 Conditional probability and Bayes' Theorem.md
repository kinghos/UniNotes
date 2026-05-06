$P[E\cap F]=P[EF]$
$$P[E|F]=\frac{P[EF]}{P[F]}$$
The sample space is all possible outcomes consistent with $F$, i.e. $S\cap F=F$
The event space is all outcomes in $E$ consistent with $F$, i.e. $E \cap F$
This assumes all outcomes are equally likely

##### Generalised chain rule
$$P[E_{1}E_{2}\dots E_{n}]=P[E_{1}]P[E_{2}|E_{1}]P[E_{3}|E_{2}E_{1}]\dots P[E_{n}|E_{1}\dots E_{n-1}]$$

##### Law of total probability
For disjoint events $F_{1},F_{2},\dots F_{n}$ such that $\bigcup F_{i}=S$,
$$P[E]=\sum^n_{i=1}P[E|F_{i}]P[F_{i}]$$
##### Bayes' theorem
$$P[F|E]=\frac{P[E|F]P[F]}{P[E]}$$
In expanded form:
$$P[F|E]=\frac{P[E|F]P[F]}{\sum^n_{i=1}P[E|F_{i}]P[F_{i}]}$$
- F is the hypothesis, E is the evidence
- $P[F|E]$ is known as the posterior
- $P[E|F]$ is known as the likelihood (probability of evidence given hypothesis)
- $P[F]$ is known as the prior (probability of hypothesis)
- $P[E]$ is known as the normalisation constant (ensures sum to 1)
#### Independence
Events $E$ and $F$ are independent if and only if $P[EF]=P[E]P[F]$
In general $n$ events are mutually independent if for every subset of these events with $r$ events where $r\leq n$
$$P[E_{a}E_{b}\dots E_{r}]=P[E_{a}]P[E_{b}]\dots P[E_{r}]$$
and $$P[E|F]=P[E]$$
Two events are conditionally independent given a third event $G$ if
$$P[EF|G]=P[E|G]P[F|G]$$
or equivalently $P[E|FG]$