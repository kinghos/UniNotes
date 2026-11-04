#### SOCs
- An ensemble of processors, memories and interconnects tailored ot an application domain
- An integrated circuit possibly containing
	- Processors (CPU, GPU, DSP)
	- Memory (ROM, RAM)
	- Interconnects (a bus or NoC)
	- External interfaces (USB, Ethernet)
	- Timing
- Tight coupling between components
- Customisable
- Can be built from different parts
#### Flynn's Taxonomy
- Classification of computer systems
- Shows parallelism in instruction and data streams
![[FlynnsTaxonomy.png]]
#### Limits on parallelism
- Performance is limited by parallelism, as speedup depends on how much the cores are used
- Amdahl's Law - shows how speedup scales with cores in parallel
$$
\text{Speedup}(n)=\frac{1}{B+\frac{1-B}{n}}
$$
- Estimates speedup for a workload when parallelising part of it
- Implies that we need to write very parallel programs to make best use of the cores (i.e. speedup is limited by the sequenc)
- Gustafson's Law