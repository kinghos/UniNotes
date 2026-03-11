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