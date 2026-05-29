#### Dice Game
- Throw a fair sided dice n times
- After each throw, you can either stop or continue
- You win if you STOP at the last 6 within the n throws
$P[\text{one 6 in last k throws}]=\frac{k}{6}\cdot\left( \frac{5}{6} \right)^{k-1}$
which is optimised for $k=5,6$

#### Secretary Problem
- Interviewing n candidates for one job in a sequential, random order
- A candidate must be accepted (STOP) or rejected immediately after the interview and cannot be recalled
- Maximise the probability of hiring the best candidate
Picking any candidate: $P[\text{hire best candidate}]=\frac{1}{n}$
Better approach: Reject the first n/2 candidates, then pick the first one better than the first n/2. $P[\text{hire best candidate}]\geq \frac{1}{4}$
Optimal strategy: Explore but reject the first $x-1$ candidates, accept the first candidate $i\geq x$ which is better than all candidates before
