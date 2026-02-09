Optimal substructure problems, usually minimising or maximising something, are amenable to dynamic programming

Dynamic programming has four steps:
1. Characterise the structure of an optimal solution
2. Recursively define the value of an optimal solution
3. Compute the value of an optimal solution, typically bottom up
4. If required, construct an optimal solution from the computed information

##### Top-Down approach
Start with the problem you want to solve, divide into sub-problems, and keep going until you reach base cases.
Requires stack space for the recursive call tree
Only solve subproblems that are required for the original problem
Avoid solving the same sub-problem twice by memoising results in a table.

##### Bottom-Up approach
Start with the base cases and solve every problem that combines them in one step, putting results into the memo table as you go
Now solve two-step problems and add those to the table. Carry on until the desired problem is encountered and solved
No recursive stack space needed
Solves subproblems that might not be useful

