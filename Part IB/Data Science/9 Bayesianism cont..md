#### Epistemology
- Epistemic uncertainty - uncertainty about the laws of nature 
- Aleatoric uncertainty - uncertainty about outcomes
For example:
- Tossing 4 coins and getting one head - very unsure about $\theta$, so high epistemic uncertainty.
- Tossing 4 million coins, pretty confident about $\theta$, so low epistemic uncertainty
- Even if we knew $\theta$, there's still uncertainty about the next coin toss. This is aleatoric uncertainty
Represent epistemic uncertainty with $\text{Pr}_{\Theta}$ and $\text{Pr}_{X}(x\mid\Theta)$ for aleatoric uncertainty

The posterior distribution depends on the amount of evidence we've seen, it quantifies epistemic uncertainty. A tighter posterior distribution means less epistemic uncertainty.
The more data we have, the closer our posterior gets to the truth
There *must* be a prior belief about every unknown parameter
If your prior is extreme, it will be reflected in your posterior

$$
\text{Pr}_{X\mid Y=y}(x)=\frac{{\text{Pr}_{X}(x)\text{Pr}_{Y\mid X=x}(y)}}{\text{Pr}_{Y}(y)}
$$
In practice, disregard $\text{Pr}_{Y}(y)$ and treat as constant $\kappa$, which is whatever is needed for this to sum/integrate to 1 over $x$.
