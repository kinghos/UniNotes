#### Cost of Max-full-heapify
Best case:
- The initial array order is compatible with the heap ordering property
- Max-full-heapify considers about n/2 keys, performs 2 comparisons per key but no swaps and no recursive calls - $\Theta(n)$
Worst case:
- Occurs when every comparison results in a swap and every recursive call also results in a swap and another recursive call.