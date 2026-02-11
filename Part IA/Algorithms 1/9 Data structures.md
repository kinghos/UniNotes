Solving a problem with a greedy algorithm: 
1. Look at your task as an optimisation problem in which we can select one move as being the locally best (greedy) option
2. Prove that there is always an optimal solution to the original problem (remembering there could be more than one) if we eagerly commit to the first move being the greedily chosen one
3. Prove the optimal substructure problem, that is, if we combine the greedy choice with the optimal solution to the subproblem that remains, we get an optimal solution to the optimal problem.

#### Activity Selection Problem
Given a set of activities that wish to use a shared resource, find a maximum-size subset of compatible activities.
Two activities are compatible if they do not wish to use the shared resource at the same time. Activities run in the interval $[s_{i},f_{i})$ i.e. another can begin at the instant a previous activity finishes.

1. Sort activities by finish time. The goal is to maximise cardinality of t