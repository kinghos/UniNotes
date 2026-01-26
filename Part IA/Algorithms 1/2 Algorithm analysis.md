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
