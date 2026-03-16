#### Hard Disks
- Stack of platters
- Transfer rate 6GB/sec
- Effective transfer rate 1GB/sec

#### SSDs
- Can be more reliable than HDDs
- No moving parts, no seek time or rotational latency
- Reads/writes wear out cells
- More expensive
- Lower capacity

#### Disk scheduling
- Disk controller receives a sequence of read/write requests from the OS that it must schedule
- FCFS - fair but efficient
- Shortest Seek Time First
	- Service requests based on distance to current head position
	- Analogous to SJF, but not optimal
- SCAN/C-SCAN
	- Start at one end of the disk and move to the other end
	- Service everything on the way
	- Consider density of requests when changing direction
	- Circular-SCAN - return back to the start when reaching the end, cylinders treated as a circular list wrapping when reaching the end

#### Disk management
- Low-level or physical formatting
	- Divides a disk into sectors, holding header information, plus data, plus error correction code
- Logical formatting to make a file system required before disk can hold files
- Disk I/O done in blocks
- File I/O done in clusters

#### Booting
- OS needs to know where to start looking - MBR
- Bootloader program executed
- Knows enough to start reading in the right blocks, starting with the partition table

#### On-disk structures
- A partition is a contiguous range of N fixed-size blocks of size k containing a file system 

#### Files
- The basic abstraction for non-volatile storage
- Many different types: data, program, documents
- Can have varied interna