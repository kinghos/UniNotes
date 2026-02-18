#### Priority Queues
A max priority queue provides insert, maximum, extract-max and increase-key operations
Max PQs are useful for schedulers to select the most important job to run next.
A min priority queue provides insert, minimum, extract-min and decrease-key operations
Min PQs are useful for ordering work items to run in a particular order

This can be implemented with a [[6 Heaps|heap]]. 
Looking at the minimum is as simple as looking at the root of the min-heap
Extracting means you swap the root with the last element and call reheapify
To insert an item, insert $\infty$ as a new element at the end of the heap, then call decrease-key with the desired value to insert at the last index.