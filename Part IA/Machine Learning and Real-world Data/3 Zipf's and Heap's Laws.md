#### Zipf's Law
Word frequency distributions obey a power law.
The nth most frequent word has a frequency proportional to 1/n
$$f_{w}\approx \frac{k}{{r_{w}}^\alpha}$$
where:
- $f_w$: frequency of word $w$
- $r_w$: frequency rank of word $w$
- $\alpha, k$: constants (which vary with the language)
e.g. $\alpha$ is around 1 for English but 1.3 for German

Zipf curves are often plotted in log-space to estimate language specific parameters $\alpha$ and $k$

We call an instance of a type a token, and an instance of a type a token. The number of types in a text is the size of the vocabulary

#### Heaps' Law
$$u_{n}=kn^\beta$$
where:
- $u_n$: number of types, i.e. vocabulary size
- n: total number of tokens, i.e. text size
- $\beta,k$: constants (language-dependent)
	- $\beta$ is around $\frac{1}{2}$
	- $30\leq k\leq 100$

Heaps' law does not saturate, there will always be more types. Going through a text means it will take longer and longer to encounter a new type.
