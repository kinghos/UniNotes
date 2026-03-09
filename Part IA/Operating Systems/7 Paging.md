- Divide physical memory into frames, fixed size blocks from 512 bytes to 1GB
- Divide logical memory into pages, blocks of the same fixed size
- Build a page table to map between pages and frames
- Page number used as an index into a page table which contains base address of each page in physical memory
- Page offset is combined with base address to define the physical memory address that is sent to the memory unit

Page table stores page table entries (PTEs) that map between logical and physical addresses

#### Pros and cons
- No external fragmentation but internal fragmentation
- On average, fragmentation is 1/2 frame per process
	- Small frames are preferred, but each frame needs a PTE
- Process view and physical memory are now very different
	- OS controls mapping so user process can only access its own memory
	- OS must track free frames
	- OS must remap page table on every context switch

#### Implementation
- Hardware support required for performance
- Page-table base register, page-table length register
- Every data/instruction access now requires two memory accesses
	- One for page table, one for data/instruction

#### Translation Lookaside Buffer
- Resolves performance issue of two lookups
- Special hardware cache with associative memory
- If translation is in the TLB, use it
- Else there is a TLB miss so do the slow lookup
- Add the entry to the TLB for faster acces next time subject to replacement policies (typically LRU)
- Can sometimes pin entries for permanent fast access
#### TLB performance
- Typically measured in terms of hit ratio
- Context switch overhead as the TLB needs to be flushed each time
	- Can store address-space identifiers to each entry to avoid this
#### Protection
- Associate protection bits with each page in the PTE
	- Accessible in kernel mode only
	- RWE to page permitted
	- Valid/Invalid bit (used later in trapping)
- As the address goes through the page hardware, protection bits are checked
- Attempts to violate protection cause a hardware trap to the OS
#### Sharing pages
- Shared code
	- Keep one copy of read only code shared among processes
	- Can be useful for IPC if read-write pages are shared
- Private code and data
	- Each process keeps its own copy of private code and data
	- Pages for which can appear anywhere in the logical address space

#### Page table structure
- Page tables can get huge, instead split into multiple levels and page out all but the outermost level
- For example, split the page number into two equal sized parts
- The PTBR then points to the address of the outermost L1 page table and lookup proceeds:

