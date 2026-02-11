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
A variable called `top` can be used to track which index is the top of the array. This can either point to the item at the top of the stack, or the first empty space.

#### Queues
Queues are FIFO data structures.
- Insert is called `enqueue`
- Delete is called `dequeue`
- Similarly to stacks, can be implemented with arrays.
Two variables are needed, head and tail - enqueue at the tail, dequeue at the head.

#### Linked Lists
A singly linked list has a pointer pointing to the head of the list, and cells of the list are tuples containing a value and a pointer to the next cell.
Consider that a list could be cyclic - an algorithm to find a key in the list could run forever if it is not present and a cyclic list!
A doubly linked list has a second pointer in each tuple, pointing to the previous element. A doubly linked list cannot be lollipop shaped.

#### Doug Lea's malloc algorithm
A program's memory ("virtual address space") contains the machine code, the stack and a very large area known as the heap.
We wish to allocate and deallocate objects within the heap, in any order.
We might allocate a large number of small objects on the heap, or a small number of large objects. Metadata for each object needs to be stored. An array is not appropriate because we would either run out of slots or waste lots of memory on more slots than needed. This can be done with a doubly linked list.

- Represent free and busy chunks, in the order they are found in memory, in a linked list.
- To allocate, we search the list for a free chunk that is at least big enough and we split it into the amount we want and the remaining free space. First is marked as busy and second is free
- To deallocate, we mark a busy chunk as free then merge it with either or both neighbours if they are also free. This coagulates free space.

- Initially, the heap is represented as a single free chunk. A sentinel node sits at the end of the linked list.
- `p = malloc(1000)` - This should set p to the base address of 1000 bytes of free space on the heap, and update the list to mark these bytes as busy. If there is not enough space anywhere in the heap, return NIL.
![[MallocAlgo.png]]
![[MallocAlgo2.png]]

Many implementations round up requests for memory to the next multiple of 4 bytes. This is more efficient for many CPUs and memory chips. Now that we know each pointer will point to a multiple of 4, we know that the least significant 2 bits of each pointer must be zeros. The free/busy bit can be stored here. This avoids the need for an extra variable in the linked list nodes, and reduces the overhead of tracking memory.