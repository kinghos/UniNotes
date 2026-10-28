#### Memory technology characteristics
- SRAM on processor chip for on-chip caches
	- Low latency, high bandwidth
- DRAM off-chip
	- Medium latency, high bandwidth
- Magnetic hard disk or flash for page-based virtual memory
	- High latency, low bandwidth
#### Principle of locality
- Programs access a small proportion of their address space at any time, giving rise to
	- Temporal locality - items accessed recently are likely to be accessed again soon
	- Spatial locality - items near those accessed recently are likely to be accessed soon
#### Direct-mapped cache
- Storing the address as a tag for every data item is a big overhead
- Amortise the cost by storing several data items per tag
	- Cache line - some number of contiguous words in memory
- Hash function is some bits of the address, the index bits
![[Direct-mapped cache.png]]
- Larger cache lines should reduce miss rate
	- But this leads to fewer cache lines, which means more competition hence an increased miss rate
	- Also leads to pollution, as data is read into the cache that may never be read
- Larger miss penalty can override benefit of reduced miss rate

#### Cache Misses
- On a miss:
	- Stall the processor pipeline
	- Fetch block from next level of hierarchy
	- Instruction cache miss
	- Data cache miss
#### Write-through
- On data-write hit, update the block in cache
- Write buffer - holds data waiting to be written to memory
#### Write-back
- Instead, on data-write hit, just update the cache-line
#### Fully associative cache
![[Fully Associative Cache.png]]
- Direct-mapped cache uses less circuit area, and more efficiently implemented
- Fully-associative caches have a higher hit rate than a direct-mapped cache
#### Set associative cache
- Have N direct-mapped caches
- Reads look in all N caches for data
- Thus the cache has N-way associativity
#### Replacement policy
- Direct mapped, no choice
- Set associative
	- Prefer non-valid entry, if there is one
	- Otherwise:
		- LRU
		- Not last used (approximates LRU)
		- Random - approx same performance as LRU for high associativity
#### Victim cache
- Augment a direct mapped cache with a tiny full-associative cache
- Evicted cache lines get a second chance in the victim cache
#### Sources of misses
- Compulsory misses i.e. first access to a block
- Capacity misses, due to finite cache size
- Conflict misses, in non-fully sa
#### Multilevel Cache
- Level-1 cache attached on the processor core
- Level-2 cache services misses from primary cache
- Occasionally L3 cache exists
- Main memory services L2 misses