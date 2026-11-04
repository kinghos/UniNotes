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
##### Amdahl's Law
- Shows how speedup scales with cores in parallel
$$
\text{Speedup}(n)=\frac{1}{B+\frac{1-B}{n}}
$$
- Estimates speedup for a workload when parallelising part of it
- Implies that we need to write very parallel programs to make best use of the cores (i.e. speedup is limited by the sequential part)
- Assumes fixed problem size
##### Gustafson's Law
- Applied when a workload can be scaled up with increased compute
$$
\text{Speedup}(n)=n+(1-n)B
$$
- Implies that when given more computing power, programmers increase the problem size, e.g. a higher resolution
- Assumes fixed execution time
#### Memory requirements
- Choose how much memory to include on-chip
- On-chip memory has tighter integration, which is good for latency and bandwidth
- Keeping memory off-chip saves space, and is more generic so has greater applicability
- Consider:
	- Does there need to be virtual memory support?
	- Should memory be centralised or distributed?
	- How does the programmer see memory?

#### Chip stacking
- Package on package
	- Memory chip on top of the SoC
	- Ball grid array connects the two
- 3D die stacking
	- Silicon wafers are directly placed together
	- Through-silicon vias connect the dies

#### DRAM
- Cell consists of 1 transistor and 1 capacitor
- Capacitor is not perfect and needs refresh
- Banks - cells organised into arrays of wordlines (rows) and bitlines (columns)
- Wordlines select the bit, and the bitline contains data to read/write
- Devices contain several banks, and each bank operates independently
- Controlled through commands sent to it
	- Row-access
	- Column read
	- Column write
	- Precharge
	- Refresh
#### Memory Controller
- Handles DRAM accesses
- Responsible for converting requests from the processors into commands for the DRAM