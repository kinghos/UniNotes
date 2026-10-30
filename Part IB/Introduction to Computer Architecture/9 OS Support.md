#### Virtual memory
- Processor + OS translates virtual to physical addresses
- Aids memory allocation
- Provides memory protection
#### Page tables
- Store virtual to physical translation information
- Page Table Entries, indexed by virtual page number
#### Page fault handler
- Page fault taken when PTE indicated that page is on disk
- Use faulting virtual address to find PTE
- Locate page on disk
- Choose page to replace
- Read page into memory and update page table
- Try to minimise page fault rate
#### Translation Lookaside Buffer
- Address translation would appear to require extra memory references
- Use a fast cache of PTEs to lookup before L1 cache access
#### Multilevel page table
- Used in RISC-V
- Page table represented as a tree
	- Compacts the structure
	- Each section of page table fits into a page
	- Supervisor address protection and translation (satp) register holds the base of the tree in the physical page number (ppn) field
	- 
