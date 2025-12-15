---
tags:
  - combinatorialCircuits
---
Volatile storage is offered by Static Random Access Memory, where data is lost once power is removed.
Buses are shared by many memory devices. If the output from the data pin on one memory was 0 and the output on another was 1, the data on that line of the data bus would be invalid.
This can be solved with
- Tristate buffers (or drivers)
- Control signals
A tristate buffer is used on the data output of the memory devices.
![[TristateBuffer.png]]
This buffer will be on each output pin of each memory device. It has 3 states compared to a normal buffer - 0, 1 and disconnected. This allows each device to send data when needed with the 0 and 1 states, otherwise stay disconnected.
These buffers are controlled with control signals, here connecting/disconnecting the buffer.
Other control signals include write enable, and chip select. These signals can be active low depending upon the particular device.