Hardware - provides basic computing resources: CPU, memory, I/O
Operating system - controls and coordinates uses of those resources
Application programs - define how those resources are used to solve the computing problems of the user
Users - motivate the whole thing

CPUs operate on data obtained from input devices and held in memory

#### Fetch-execute cycle
The CPU repeatedly fetches and decodes the next instruction, generating control signals and operand information
Inside the execution unit, control signals select the functional unit and operation
- If the ALU read one/two registers, perform operation, write result back
- If Branch Unit, test condition and maybe add value to PC
- If Memory Access Unit, generate address and use bus to read/write value

#### Buses
- Shared communication wires
- Low cost and versatile, but a potential bottleneck
- Typically comprises:
	- address lines determining how many devices on a bus
	- data lines determining how many bits transferred at once
	- control lines indicating target devices and selected operations
- Operates in an initiator-responder manner:
	- Initiation decides to read data
	- Initiator puts address onto bus and asserts read
	- Responder reads address from bus, retrieves data, and puts onto bus
	- Initiator reads data from bus
##### Bus hierarchy
- Different buses have different characteristics
- Processor bus is often the fastest and widest so the CPU can talk to cache
- Memory bus to communicate with memory
- PCI buses to talk to other devices
- Bridges forwards from one side to another

#### Booting
- Bootstrap program (bootloader) executes when machine powered on
	- Traditionally BIOS in ROM, now more complex UEFI
	- Initialises all parts of the system, memory, device controllers
	- Finds, loads and executes the kernel, possibly in stages
- Kernel enables processes to be created, devices to be read/written and file system to be accessed
- System processes will then start

#### System operation
- I/O devices and CPU execute concurrently
- Each device controller is responsible for a particular device type and has a local buffer
- CPU moves data from/to main memory to/from local buffers
- Device controller informs the CPU that it has finished its operation by raising an interrupt

#### Interrupts
- Device controllers communicate with CPU via interrupts
	- Controller controls interaction between device and local buffer
	- CPU moves data between main memory and device buffer
- Interrupts decouple CPU requests from device responses
- Controller informs CPU it is finished by raising an interrupt
- A raised interrupt must be handled
	- Transfer control to the ISR via the interrupt vector, a table containing addresses of all the ISRs
	- Interrupt architecture saves the address of the interrupted instruction
	- After reading from this device, CPU resumes using a special instruction
- A trap or an exception is a software-generated interrupt

#### Storage
- A word is a given computer's native unit of data, one or more bytes, e.g. a 64-bit computer has 8-byte words
- In this course, a kilobyte is considered to be 1024 bytes
![[StorageComparison.png]]

#### Layering
Layering is a means to manage complexity by controlling interactions between components
- Arrange components in a stack and restrict a component at layer X from relying on any other component except the one at the later below, and providing service to any component except the one at the layer above
- Multiplexing is where one resource is being consumed by multiple consumers at once
#### Latency
- Latency is how long something takes
- Bandwidth is the rate at which something occurs (throughput)
- Jitter is the variation in latency

#### Caching
