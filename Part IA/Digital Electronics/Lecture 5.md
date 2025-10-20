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