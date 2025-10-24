#### Shift register
A shift register can be implemented using a chain of D-type FFs
![[ShiftRegister.png]]
$D_{in}$ is a serial input and $Q_0,Q_1,Q_2$ are parallel outputs

![[ShiftRegisterTiming.png]]
Data moves one position to the right on application of each clock edge

Asynchronous Preset and Clear inputs on the FFs can be utilised to provide parallel data input
Data can be clocked out through $Q_2$ in a serial fashion. This can be used as the basis for a serial data link.
![[SerialDataLink.png]]
One data bit can be sent at a time across the link. This needs fewer wires than a parallel data link.

#### System Timing
The clock period, $T_c$, is the time between the rising edges of a repetitive clock signal. 
Clock frequency is the reciprocal of the clock period.

![[TimeConstraints.png]]
Maximum propagation delay, $t_{pd}$ , enables the worst case setup time to be satisfied. Minimum clock period is given by $$
T_{c}\geq t_{pc}+t_{pd}+t_{su}
$$
Clock period is often set by manufacturer, so the equation for propagation delay through combinational logic is $$
t_{pd} \leq T_{c}-(t_{pc}+t_{su})
$$
![[Pasted image 20251024112730.png]]
D cannot change in a time shorter than $t_{hold}$. Therefore $$
(t_{pc}+t_{pd})min \geq t_{hold}
$$
A reliable FF must have a minimum hold time less than the minimum propagation delay time, as you would expect 2 FFs directed cascaded without any combinational logic between them to have no timing issues. Often FFs are designed with $t_{hold}=0$, satisfying this condition.

Clock skew is the problem of clock edges reaching each FF at different times, owing to different wire lengths and other small delays.
Clock stew reduces propagation delay (bad), but increases hold time (good).

#### Metastability
It is not always possible to control when a FF input changes in relation to the clock edge. This can happen when the input signal comes from a user e.g. a button
![[Metastability.png]]
This invalid state will eventually fall onto one of the two valid states. The time taken for this to happen can be modelled by this equation. $$
P(t_{res}>t) = \frac{T_{0}}{T_{c}}e^{-\frac{t}{\tau}}
$$
where $T_c$ is the clock period, and $T_0$ and _$\tau$_ are characteristics of the FF
$\frac{T_{0}}{T_{c}}$ can be seen as the probability that the input changes at a 'bad' time since it decreases with increasing $T_c$, and $\tau$ is a time constant indicating how fast the FF will exit the metastable state.

A synchroniser can be used to to minimise metastability.
![[Pasted image 20251024114802.png]]
Here, if $T_c$ is long enough, $D_1$ will resolve to a valid level with high probability. This means FF1 has a valid input that satisfies its setup and hold times and yields valid output Q. 
The synchroniser fails if output Q becomes metastable. The probability of failure for a single input change is 
$$
P_{fail}=\frac{T_{0}}{T_{c}}e^{{ - \frac{T_{c}-t_{su}}{\tau} }}
$$
If $D_0$ changes once per second, the probability of failure per second is just $P_{fail}$.
System reliability is measured as the *mean time between failures* (MTBF).
$$
MTBF = \frac{1}{{P_{fail}}/{s}}=\frac{T_{c}e^{\frac{T_{c}-t_{su}}{\tau}}}{NT_{0}}
$$
