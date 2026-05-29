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