### Sequential logic
- A snapshot of memory is called the state
- A one bit memory is often called a bistable, i.e. it has 2 stable internal states
- Flip-flops and latches are particular implementations of bistables

#### Latches
![[RSLatch.png]]
This is a memory element with 2 inputs, Reset and Set, and two outputs, $Q$ and $\bar{Q}$


![[NORTruthTable.png]]
When $R=1, S=0$ then Gate 1 will always output 0, and Gate 2 will complement S, so $Q=0,\bar{Q}=1$.
Following this, if $R=0, S=0$, then Gate 2 remains in complement condition, and Gate 1 goes into complement condition. This leads to "holding" $\bar{Q}=1, Q=0$

![[RSLatchStateTransitionTable.png]]