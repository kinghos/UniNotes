Most sequential circuits employ the notion of synchronous operation - the output of a sequential circuit is constrained to change only at a time specified by a global enabling signal (the clock)

#### Transparent D Latch

![[TransparentDLatch.png]]
If one of the inputs is 0, the output is always 0
Output follows b input if a is 1
The complement function prevents $R=1,S=1$ (illegal avoided)

#### Master-Slave Flip-Flops
The D latch is "level" triggered. It exhibits transparent behaviour if EN=1. Designing circuits to trigger on an edge trigger is often simpler.

![[MasterSlaveFlipFlop.png]]
Both latch inputs are effectively connected to the clock.

The Master-Slave configuration has been replaced by F-F circuits which are easier to implement with better performance.

#### J-K Flip-Flop
The illegal state is replaced with a toggle state.
![[JKFlipFlop.png]]
#### T Flip-Flop
J-K Flip-Flop with its J and K inputs connected together and renamed as T.
![[TFlipFlop.png]]
#### Asynchronous inputs
Inputs can be taken independently of any clock or enable inputs, usually:
- Reset/Clear - force Q to 0
- Preset/Set - force Q to 1
These can be used to force a synchronous circuit into a known state, e.g. at start up.

- Setup time: the minimum duration that the data must be stable at the input before the clock edge
- Hold time: the minimum duration that the data must remain stable on the FF input after the clock edge
![[DelayTimingFlipFlop.png]]