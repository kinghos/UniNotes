Decoding: finding the most likely hidden state sequence $X$ that explains the observation $O$ given the HMM parameters $\mu=(A,B)$
$$\begin{align}
\hat{X}&=\text{argmax}P(X,O|\mu) \\
&=\text{argmax}\prod^T_{t=1}P(O_{t}|X_{t},B)P(X_{t}|X_{t-1},A)
\end{align}$$


#### Viterbi
- Generate transition matrix
- Generate emission probability matrix
- Draw up table, where rows are hidden states and columns are observations