Solving a problem with a greedy algorithm: 
1. Look at your task as an optimisation problem in which we can select one move as being the locally best (greedy) option
2. Prove that there is always an optimal solution to the original problem (remembering there could be more than one) if we eagerly commit to the first move being the greedily chosen one
3. Prove the optimal substructure problem, that is, if we combine the greedy choice with the optimal solution to the subproblem that remains, we get an optimal solution to the optimal problem.

#### Activity Selection Problem
Given a set of activities that wish to use a shared resource, find a maximum-size subset of compatible activities.
Two activities are compatible if they do not wish to use the shared resource at the same time. Activities run in the interval $[s_{i},f_{i})$ i.e. another can begin at the instant a previous activity finishes.

Sort activities by finish time. The goal is to maximise cardinality of the set of activities. If we are solving $S(i,k)$ with some set A of activities to choose from, we pick an activity $a_{j}\in A$ and note the number of activities would be $$1+|S(i,s_{aj})|+|S(f_{aj},k)|$$
where the two recursive calls have a filtered subset of A containing only those activities that are compatible with $a_j$ (i.e. do not overlap in time with $a_{j}$)
$$S(i,k)=\text{argmax}_{j}\{ a_{j} \}\cup S(i,a_{j})\cup S(f_{aj},k)$$
(use dynamic programming for this)

### Data structures
Each item in memory begins at some point in the memory, known as the objects base address. Pointers point to this base address. NIL is a reserved pointer value that does not refer to any object.

#### Stacks
Stacks are LIFO data structures.
- Insert is called `push`
- Delete is called `pop`
- A stack with a fixed maximum capacity can be stored with an array. To store one with an unbounded capacity, a linked list can be used or an array with the capability of copying to a larger array if needed
