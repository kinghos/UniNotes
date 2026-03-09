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
	- Entry is now marked valid a
- After handling the fault, restart the instruction that caused the fault