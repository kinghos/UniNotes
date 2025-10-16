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