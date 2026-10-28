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