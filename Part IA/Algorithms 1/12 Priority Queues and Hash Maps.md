#### Priority Queues
A max priority queue provides insert, maximum, extract-max and increase-key operations
Max PQs are useful for schedulers to select the most important job to run next.
A min priority queue provides insert, minimum, extract-min and decrease-key operations
Min PQs are useful for ordering work items to run in a particular order

This can be implemented with a [[6 Heaps|heap]]. 
- Looking at the minimum is as simple as looking at the root of the min-heap
- Extracting means you swap the root with the last element and call reheapify
- To insert an item, insert $\infty$ as a new element at the end of the heap, then call decrease-key with the desired value to insert at the last index.

This can also be implemented with a [[11 Trees cont.#Red-Black Trees|Red-Black Tree]].
- Looking at the minimum is as simple as getting the minimum of the tree. 
- Extracting the minimum can be done by simply deleting the node
- Decreasing the key is just deleting then inserting
- Inserting is simply using the insert function for RBTs.

![[PQCosts.png]]
#### Hash Tables
**We will index hash tables from 0.**
##### Direct addressing
CPUs can LOAD data from memory and STORE data to memory but those machine code instructions need a memory address. The data type of array elements is fixed and known in advance. This tells us the size, X, in bytes of each entry. Direct addressing translates programming language syntax like `T[i]` into a CPU LOAD or STORE instruction

To support non-integers as the key, a hash function is used to convert it to an integer.