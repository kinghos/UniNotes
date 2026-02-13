#### Non-deterministic finite automaton
An NFA is defined to be a tuple $M=(Q,\Sigma,\Delta,s,F)$
1. $Q$ is a set of states
2. $\Sigma$ is an alphabet
3. $\Delta$ is a ternary relation $\Delta:Q\times \Sigma \nrightarrow Q$ called the transition relation
4. $s$ is an element of $Q$, the starting state
5. $F$ is a subset of $Q$, the accepting states
The idea of an NFA is that you feed it a string after initialising it to its starting state, and then you explore the transitions it makes by biting off characters from the string until it is consumed. If the automaton ends up in an accepting state then the string is accepted, otherwise, the string is considered rejected.

$$\mathcal{L}(M)=\{ u\in \Sigma^* \mid \exists q\in F.s \xrightarrow{u}^*\  q \}$$
The relation $q\xrightarrow{u}^* q$ is defined 
$$\begin{align}
q \xrightarrow{\epsilon} q' &\iff q=q' \\
q \xrightarrow{au}q' &\iff \exists q'' \in Q.q \xrightarrow{a}q'' \land q'' \xrightarrow{u} q' 
\end{align}$$
