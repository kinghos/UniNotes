#### Independence
Two random variables $X$ and $Y$ are independent if for all values $a,b$
$$P[X\leq a,Y\leq b]=P[X\leq a]\cdot P[Y\leq b]$$
With the joint probability distribution
$$F(a,b)=F_{X}(a)\cdot F_{Y}(b)$$
The definition of independence of $X$ and $Y$ implies the following factorisation formula: for any suitable sets $A$ and $B$
$$P[X\in A,Y\in B]=P[X\in A]\cdot P[Y\in B]$$
$$f_{X,Y}(x,y)=f_{X}(x)\cdot f_{Y}(y)$$
#### Covariance
$$\text{Cov}[X,Y]=E[(X-E[X])\cdot (Y-E[Y])]$$
If $\text{Cov}[X,Y]>0$ and $X$ is larger than $E[X]$, then $Y$ will likely be smaller than $E[Y]$ (and vice versa for $\text{Cov}[X,Y]<0$)
$\text{Cov}[X,Y]$ corresponds to correlation. Independent variables have a covariance of $0$
