#### Physical memory
- Memory split into zones based on hardware characteristics
- Page allocator allocates and frees all physical pages
- Buddy-heap algorithm to track available pages
	- Each allocatable memory region is paired with adjacent partner
	- Two allocated partner regions freed together are combined into a larger region
	- A larger region can be subdivided to fit a smaller memory request
- Slab allocation is used in the kernel
#### Virtual memory
Paging system uses page-out policy
Virtual address spaces are created for two reasons:
- Process runs new program via exec
	- Process is given its own virtual-address space
- Process creates a new process via fork
	- Copy of the parent's virtual address space
	- Copies parent's page tables into the child's
#### File system
- The inode object structure represents an individual file
- The file object represents an open file
- The superblock object represents an entire file system
- A dentry object represents an individual directory entry
- Files can have object IDs matching either a UID or a GID