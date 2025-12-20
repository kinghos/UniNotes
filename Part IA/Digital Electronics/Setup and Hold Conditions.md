---
tags:
  - sequentialCircuits
---
The clock period, $T_c$, is the time between the rising edges of a repetitive clock signal. 
Clock frequency is the reciprocal of the clock period.

![[TimeConstraints.png]]
Maximum propagation delay, $t_{pd}$ , enables the worst case setup time to be satisfied. Minimum clock period is given by $$
T_{c}\geq t_{pc}+t_{pd}+t_{su}
$$
Clock period is often set by manufacturer, so the equation for propagation delay through combinational logic is $$
t_{pd} \leq T_{c}-(t_{pc}+t_{su})
$$
![[HoldTime.png]]
D cannot change in a time shorter than $t_{hold}$. Therefore $$
(t_{pc}+t_{pd})min \geq t_{hold}
$$
A reliable FF must have a minimum hold time less than the minimum propagation delay time, as you would expect 2 FFs directed cascaded without any combinational logic between them to have no timing issues. Often FFs are designed with $t_{hold}=0$, satisfying this condition.

Clock skew is the problem of clock edges reaching each FF at different times, owing to different wire lengths and other small delays.
Clock skew reduces propagation delay (bad), but increases hold time (good).