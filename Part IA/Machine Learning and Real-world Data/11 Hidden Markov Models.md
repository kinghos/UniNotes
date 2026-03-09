can you Two types of weather: rainy and cloudy. The weather doesn't change during the day.
We can use a history of weather observations
$P(w_{t}=Rainy\mid w_{t-1}=Rainy, w_{t-2}=Cloudy, \dots)$
Markov assumption (first order) $P(w_{t}\mid w_{t-1}, w_{t-2}\dots w_{1})\approx P(w_{t}\mid w_{t-1})$
The joint probability of a sequence of observations/events can be approximated as 
$$P(w_1,w_{2},\dots,w_{t})\approx \prod^n_{t=1}P(w_{t}\mid w_{t-1})$$
![[MarkovModels.png]]
A Markov Chain is a stochastic process that embodies the Markov Assumption.
Can be viewed as a probabilistic finite-state automaton. States are fully observable, finite and discrete; transitions are labelled with transition probabilities. Models sequential problems

Hidden states need to be inferred from the sequence of observations

Markov (Limited Horizon) Assumption: Probability of an output observation depends only on the current state and not on any other states or any other observations.

$a_{ij}$ is the probability of moving from state $s_{i}$ to state $s_{j}$
$$a_{ij}=P(X_{t}=s_{j}\mid X_{t-1}=s_{i})$$
$$\forall_{i}\sum^{N+1}_{j=0}a_{ij}=1$$
Special start state and end state are not associated with real observations