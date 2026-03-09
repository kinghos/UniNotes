#### Amortised analysis
Sometimes a worst-case analysis is too pessimistic
Three methods of amortised analysis:
- Aggregate analysis
- The accounting method
- The potential method

#### Vector insert aggregate cost
For a vector, when it is full and new items are to be inserted, a new array is allocated with double the size and the elements are copied across. Normally the worst case would assume resizing is necessary.
The aggregate cost is found by considering how many operations are needed as the vector grows, e.g. with an array of 16 elements, adding an element will have a cost of 17 (16 to copy and 1 to add) and then 15 operations (to get to 32) before the next being 32+1, and so on. For $N=2^k$ insertions, this sums to $O(N)$, dividing by $N$ gives $O(1)$ as the aggregate cost

#### Accounting method
- The amortised cost for each operation is declared as the amount we charge our customer.
- Amortised costs might exceed the actual costs, with the excess going into a "credit" account
- When an amortised cost is less than the actual cost, the credit pays for the shortfall
- This yields a valid set of amortised costs provided for any sequence of operations. The total amortised cost is an upper bound for the actual cost, and the credit never goes negative

#### Potential method
- Similar but does not attribute credit to particular operations or items
- Instead, measures the potential of te