- Virtual addressing provides the option of virtual memory
- Already have valid/invalid page translations, introduce a "non-resident" designation and put these pages on a non-volatile store
- Processes access non-resident memory just as if it were the real thing
- Separates program logical memory from physical memory, allowing logical address space to be much larger than physical address space
- Implemented via demand paging and demand segmentation
#### Benefits
- Portability - programs can work regardless of the size of physical memory
- Convenience - Less of the program needs to be in memory at once, thus potentially more efficient multiprogramming, less I/O loading/swapping, large sparse data structures easily supported
- Efficiency - no need to waste real memory on code or data which isn't used

#### Virtual address space
- Gives the logical view of how process is stored in memory
- Physical memory organised in page frames
- Usually stack starts at maximum logical address and grows down while heap grows up
- No physical memory needed until heap or stack grows to a new page
- System libraries shared via mapping into virtual address space

#### Page faults
- When an invalid page is referenced, it causes a trap to the OS - a page fault
- OS handles the trap by examining another table
	- If invalid memory reference, then abort
	- If valid but not resident, find a free frame and swap the page in
	- Entry is now marked valid as page is in memory
- After handling the fault, restart the instruction that caused the fault

#### Instruction restart
- For a complex instruction, the instruction cannot be restarted from the state if it has already modified state
- Handle by going across each block, touching every page to ensure valid so no fault can occur
- If the page fault handler triggers a fault, just give up (double fault)

#### Locality of reference
- In a short time interval, the locations referenced by a process tend to group into a few regions of its address space
- e.g. procedure being executed, sub-procedures, data access, stack variables

#### Demand paging
- Could bring entire process into memory at load time, or bring pages into memory as needed
	- Reduces I/O and memory needed and response time
	- Supports more running processes
	- Pure demand paging starts with every page marked invalid
- Hardware support required
	- Page table with valid/invalid bit
	- Secondary memory (swap device with swap space)
	- Ability to restart instruction
- Lazy swapper or pager never swaps a page into memory unless page will be needed

In the worst case, there is a page fault, and the cause of the page fault needs to be found. This involves an interrupt so that another process can run while the fault is being found. This leads to lots of context switching.

#### Effective Access Time
Let $p$ be he probability of a page fault, 0 being no page faults and 1 being every reference causes a page fault
$$\text{EAT}=(1-p)\times\text{memory access time} + p\times\text{page fault service time}$$
#### Demand paging optimisations
- Swap space I/O can be faster than file system I/O even on the same device
- Demand page program from binary on disk - discard when freeing unmodified frame
- Copy-on-write
	- Both parent and child processes initially share the same pages in memory
	- Only when a process actually modifies a shared page is the page copied
	- COW allows more efficient process creation as only modified pages are copied
- Allocate free pages from a pool of zero-fill on-demand pages
- vfork variation of fork has child created as copy-on-write address space of parent

#### Page replacement
- Paging in from disk requires a free frame, but physical memory is limited
- Either unused pages are discarded or swap out an entire process
- Page fault handler must
	1. Locate the desir