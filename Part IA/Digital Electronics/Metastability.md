---
tags:
  - sequentialCircuits
---
It is not always possible to control when a FF input changes in relation to the clock edge. This can happen when the input signal comes from a user e.g. a button
![[Metastability.png]]
This invalid state will eventually fall onto one of the two valid states. The time taken for this to happen can be modelled by this equation. $$
P(t_{res}>t) = \frac{T_{0}}{T_{c}}e^{-\frac{t}{\tau}}
$$
where $T_c$ is the clock period, and $T_0$ and _$\tau$_ are characteristics of the FF
$\frac{T_{0}}{T_{c}}$ can be seen as the probability that the input changes at a 'bad' time since it decreases with increasing $T_c$, and $\tau$ is a time constant indicating how fast the FF will exit the metastable state.

A synchroniser can be used to to minimise metastability.
![[Delays.png]]
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
