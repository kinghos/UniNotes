### Priority Queues
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
### Hash Tables
**We will index hash tables from 0.**
#### Direct addressing
CPUs can LOAD data from memory and STORE data to memory but those machine code instructions need a memory address. The data type of array elements is fixed and known in advance. This tells us the size, X, in bytes of each entry. Direct addressing translates programming language syntax like `T[i]` into a CPU LOAD or STORE instruction

#### Hashed addressing
To support non-integers as the key, a hash function is used to convert it to an integer.

Problems with hashed addressing:
- Range: The integer output of the hash function is used as a table index. Often the size of a hash table needs to be changed. The solution is to require that across all possible inputs a hash function must output a uniformly distributed unsigned integer in some range. This can be done through modulo for instance
- Performance: It is difficult to get a function that is uniformly distributed like this, especially when you know nothing about the inputs that a particular program might use as hash keys. Hence real world hash functions are very complex and slow-running
- Collisions: if we are mapping strings of any length into 32 bit integers, there are necessarily collisions, by the pigeonhole principle: there are more possible hash keys than possible hash values so at least one hash value must be used more than once
- Entropy: If keys are short or very similar, there is not enough entropy to map them to different places in the table. If the keys are simple letters of the alphabet, there are only 26 possible inputs, hence at most 26 different outputs, thus not giving a uniform distribution

#### Solutions to collisions
##### Chaining
Entries in the hash table are pointers to linked lists, initialised as NIL.
List cells are (key, payload, pointer) tuples where pointer is the pointer to the next cell

The load factor, $\alpha=\frac{n}{T.size}$, where $n$ is the number of live keys stored in the table, and $T.size$ is the total size of the hash table.

Lists can also be sorted by key. This requires the keys to be comparable.
Alternatively, the key can be pushed onto the head of the list. The list can contain the same key repeatedly. Delete will now push a cell to the head with NIL as the payload. Or, delete can delete the first instance of the key. This means it will only undo the most recent insert

#### Open Addressing
Go down from the key, and keep going until an open slot is found. If an open slot is not found (you have wrapped around all the way to the key again), then fail.
The build up of long probe sequences that do not even contain keys with the same hash value is called primary clustering
An alternative probe sequence is
$$\text{probe}(T,\text{key},i) =(h(key)+ai +bi^2) \mathrel{\%} \text{T.size}$$
This hits every position provided at least one of a and b is non zero and less than the size, which is prime. This is prone to secondary clustering, which means keys which hash to the same value will collide with each other at every probe position.
Double hashing solves this problem. Using two hash functions added together means their probe sequences step apart.