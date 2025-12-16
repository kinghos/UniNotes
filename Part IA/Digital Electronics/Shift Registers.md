---
tags:
  - sequentialCircuits
---
A shift register can be implemented using a chain of [[D Flip-Flop|D-type FFs]]
![[ShiftRegister.png]]
$D_{in}$ is a serial input and $Q_0,Q_1,Q_2$ are parallel outputs

![[ShiftRegisterTiming.png]]
Data moves one position to the right on application of each clock edge

[[Asynchronous inputs|Asynchronous]] Preset and Clear inputs on the FFs can be utilised to provide parallel data input
Data can be clocked out through $Q_2$ in a serial fashion. This can be used as the basis for a serial data link.
![[SerialDataLink.png]]
One data bit can be sent at a time across the link. This needs fewer wires than a parallel data link.
