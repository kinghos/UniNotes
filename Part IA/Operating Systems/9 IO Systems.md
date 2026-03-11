- Range of IO devices
	- Human readable e.g. displays, keyboards, mice
	- Machine readable e.g. disks, tapes, CDs
	- Communications e.g. modems, network interfaces
- Each has its own data rate, control complexity, transfer unit and direction, data representation, error handling
#### I/O Subsystem
- Signals from I/O devices interface with computer
- A device has at least one connection point known as a port
- Devices interconnect via a bus, either daisy chained or shared direct access
- Devices have integrated or separated controllers containing processor, microcode, private memory, etc. that operate the device, handle bus connections and any ports
- Typically device will have registers to hold commands addresses, data
- Devices have addresses and are used by either
	- Direct I/O instructions, usually privileged
	- Memory mapped I/O, where device registers are mapped into processor address space especially when large

#### Polling
- Host repeatedly reads device-busy until clear
- Host sets read or write bit in command register, and puts data into data register
- Host sets command-ready bit in status register
- Device sees command-ready and sets device-busy
- Device performs requested operation, executing transfer
- Device clears command-ready and any error bit and then clears device busy
Waiting for device-busy to be clear is polling, a busy-wait cycle

#### Interrupts
- More efficient than polling when device is relatively infrequently accessed
- Device triggers interrupt-request line
	- Checked by the CPU after each instruciton
	- Aligns interrupts with instruction boundaries
- Interrupt handler receives the interrupt unless masked
- Interrupt vector dispatches interrupt to correct handler
	- Context switch required before and after
	- Priorities applied, and some interrupts may be non-maskable
#### Handling interrupts
- Spit into two parts:
	- Bottom half, the interrupt handler
	- Top half, interrupt service routines
- Processor-dependent interrupt handler may
	- Save more registers and establish a language environment
	- Demultiplex interrupt in software and invoke relevant ISR
- Device-dependent ISR will:
	- For programmed I/O device: transfer data and clear interrupt
	- For DMA devices: acknowledge transfer, request any more pending, signal waiting processes, and finally enter the scheduler or return

#### Direct Memory Access
Used for high-speed I/O devices able to transmit information at close to memory speeds
- Interrupts are good but livelock a problem
- Better if devices can read and write processor memory directly (DMA)
- Device controller transfers blocks of data from buffer storage directly to main memory without CPU intervention with generic DMA command
	- Source address plus increment/decrement/do nothing
	- Sink address plus increment/decrement/do nothing
	- Transfer size
- Only generate one interrupt per block rather than one per byte
- DMA channels may be provided by dedicated DMA controller or by devices themselves
- All that's required is that a device can become a bus master
- Scatter/Gather DMA chains multiple requests of disk reads into set of buffers

#### I/O Device Characteristics
- Block devices, e.g. disk drives
	- Commands include read, write, seek
	- Can have raw access via filesystem or memory-mapped
- Character devices, e.g. mice and keyboards
	- Commands include get, put
	- Layer libraries on top for line editing, etc.
- Network devices
	- Vary enough from block and character devices to get their own interface
	- Unix and Windows NT use the Berkeley Socket interface
- Misc
	- Current time, elapsed time, timers, clocks

#### Blocking, non blocking and asynchronous I/O
- Blocking
	- Process suspended until I/O completed
- Non blocking
	- I/O call returns all available data, immediately
	- Returns count of bytes read/written, maybe 0
	- select following read/write
	- Relies on multi threading
- Asynchronous
	- Process continues running while I/O executes with I/O subsystem explicitly signalling I/O completion
	- Most flexible and potentially most efficient, but also most complex to use.