Given a function and its minterms, the QM method is more effective at simplifying the linear algebra than Karnaugh maps

1. Create a table with 3 columns:
	- Group: the number of ones
	- Minterm
	- Binary representation of minterms
2. Make a second table with 3 columns:
	- Group
	- Matched pairs - comparing minterms in adjacent groups, and finding those that only differ by one variable
	- Binary representiation - mark the changing variable with an X
3. Repeat with another table, marking matched pairs where only one variable changes
4. Continue until there are no matched pairs. Write down the Boolean representation of each prime implicant, and go back through all previous tables and see there are any minterms/minterm groups with no matched pairs (hence also prime implicants)
5. Lastly, make one last table with the prime implicants and their corresponding minterms
6. 