For all positive integers m and n,
1. $n\cdot lc_{2}(m,n)\equiv gcd(m,n) \pmod m$
2. whenever $gcd(m,n)=1$, $[lc_{2}(m,n)]_{m}$ is the multiplicative inverse of $[n]_{m}$ in $\mathbb{Z}_{m}$

#### Encryption (non examinable?)
Encrypt and decrypt by means of modular exponentiation:
$$[k_{e}]_{p}, [\ell^d]_{p}$$
By Fermat's Little Theorem:
$$k^{1+c\cdot(p-1)}\equiv k \pmod p$$
Consider $d,e,p$ such that $e\cdot d=1+c\cdot(p-1)$, equivalently
$$d\cdot e\equiv 1 \pmod {p-1}$$

### Induction
Base case, inductive case
Assuming $P(n)$ is the induction hypothesis