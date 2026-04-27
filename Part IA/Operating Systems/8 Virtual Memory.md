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
	1. Locate the desired replacement page on disk
	2. Select a free frame for the incoming page (or if there is none select a victim)
	3. Read desired page into the new free frame
	4. Restart the faulting process
- No free frames - doubles page fault service time

#### Algorithms
- Want the lowest page fault on both first and subsequent access
- Evaluate using a sequence of page numbers, noting repeated access to the same page does not trigger a fault
- Assume three frames are available (for this example)
- Belady's anomaly - increase in page frames results in an increase in page faults
##### FIFO
- Susceptible to Belady's anomaly
##### OPT
- OPTimal
- Replace page that will not be used for the longest time
- Not obvious: hard to predict
- Useful as a benchmark
##### LRU
- Approximate OPT
- Assume that the recent past is a good predictor of the future
- Replace the page not used for the longest time
- Better than FIFO but worse than OPT
- Is not susceptible to Belady's anomaly
- Can be implemented with counter based on clock, or with a stack

#### Approximating LRU
- Use a reference bit in the PTE, initially 0 and set to 1 when page touched
- Not Recently Used replacement
	- Periodically clear reference bits
	- Victimise pages according to reference bits
- Second-chance clock algorithm
	- Store pages in queue as per FIFO, often with a circular queue and a current pointer
	- Discard current if reference bit is 0 else reset reference bit and increment current
	- Guaranteed to terminate after at most one cycle, devolves into a FIFO if all pages are referenced
- Can emulate reference bit if no hardware support
	- Mark the page as no access to clear the reference bit

Other algorithms include Least Frequently Used and Most Frequently Used

#### Page buffering algorithms
- Keep a minimum sized pool of free frames, always available
- Possibly keep list of modified pages
- Possibly keep free frame contents intact and note what is in them
- Alternatively stop having the OS guess about future page access

Page replacement performance can be minimised by considering a curve of page-fault rate against number of physical frames and minimising the area under the curve.

#### Frame allocation
- Need an allocation policy to determine how to distribute frames
- Objectives: fairness, minimise system-wide page-fault rate, maximise level of multiprogramming
#### Global/local allocation
- Most replacement schemes are global, so any page could be a victim
- Alternatively, local replacement means each process selects only from its own set of allocated frames
- More consistent per-process performance but possibly underutilised memory
#### Thrashing
- A process without "enough" pages has high page-fault rate
- Occurs when size of locality > total memory
#### Working set
- Avoid thrashing by considering the working set
	- Pages required at the same time for a process to make progress
- If total number of pages referenced in the most recent window is greater than the number of frames, suspend/swap out a process
- Pre-paging: bring in working set pages when starting a process