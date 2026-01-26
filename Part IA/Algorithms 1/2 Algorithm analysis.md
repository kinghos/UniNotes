Consider
- Memory requirements (space complexity)
- CPU time (time complexity) 
- Disk operations
To measure these, we need to measure the size of an input instance succinctly
in some cases operations that may seem to take constant time may take longer, e.g. finding the length of an array - sometimes the length may be beyond the integer limit, in which case the value will be stored with arbitrary precision arithmetic (where numbers are arrays of digits)

Considerations from pseudocode:
- Memory cells e.g. elements in an array, can only hold one item
- Indexing an array takes 1 unit of time
- Arithmetic operations take 1 unit
- Comparisons take 1 unit
- Assignments to variables take 1 unit

#### Cost of insertion-sort
![[InsertionSortCost.png]]
The running time, $T(n)$, on inputs of size n is the cost of each line multiplied by the number of times the line is executed.

Best case: $T(n)=an+(b+c+g)(n-1)+d\sum^n_{j=2}t_{j}+(e+f)\sum^n_{j=2}(t_{j}-1)$
This is when the data is in sorted order, i.e. $t_{j}=1$
This leaves a linear time complexity of $O(n)$
In the worst case, the data i