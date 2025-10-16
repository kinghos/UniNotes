Half adder - adds two single bit binary numbers together, with a $sum$ and $C_{out}$ output
Full adder - Adds two single bit binary numbers together with a carry input, and $sum$ and $C_{out}$ outputs

##### Full adders
$$sum=c_{in}\oplus a\oplus b$$
$$
C_{out}=b.a+c_{in}.(b+a)
$$
Ripple Carry Adders are a chain of full adders, where the $C_{out}$ of one adder leads into the $C_{in}$ of the next. This allows the addition of $n$ bit binary numbers.
Complementing one of the numbers and setting $C_0$ to one would act as subtraction
![[Ripple Carry Adder Diagram.png]]

##### Fast carry generation
Fast carry generation is an alternative way of managing carry signals. Using it means that you do not have to wait for the carry signals to ripple between full adders before the output is valid

Three parts:
- Carry kill -> $k_{i}=\bar{a_{i}}.\bar{b_{i}}$
- Carry propagate -> $p_{i}=a_{i}\oplus b_{i}$
- Carry generate -> $g_{i}=a_{i}.b_{i}$

To reduce complexity, only 4-bit adder blocks are implemented with only up to $C_{4}$ generated using fast generation. This is then carried into the next 4-bit adder block, and within each 4-bit adder block, conventional RCA is used.