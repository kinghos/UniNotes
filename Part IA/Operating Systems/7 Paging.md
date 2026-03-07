- Divide physical memory into frames, fixed size blocks from 512 bytes to 1GB
- Divide logical memory into pages, blocks of the same fixed size
- Build a page table to map between pages and frames
- Page number used as an index into a page table which contains base address of each page in physical memory
- Page offset is combined with base address to define the physical memory address that is sent to the memory unit

Page table stores page table entries (PTEs) that map between logical and physical addresses