#### Multiplexers
A multiplexer chooses 1 of many inputs to steer to its single output under the direction of control inputs. e.g. if the input to a circuit can come from several places a Mux is one way to funnel the multiple sources selectively to the single output.

![[MultiplexExample.png]]

This is an 8:1 Mux, which needs 3 control inputs.
![[MultiplexExample2.png]]
The control inputs (in this case $x, y,z$) determine which input is output, e.g. $010$ would output $I_{2}$ which is 0.

#### Demultiplexers
A demultiplexer is the opposite of a Mux, i.e. a single output is directed to exactly one of its outputs

This is a 1:2 Demux
![[DemultiplexerExample.png]]
Here, the control inputs determine which output is selected.
Larger Demux are possible, e.g. a 3:8 Demux has 3 control inputs and 8 outputs.

#### Decoders
A decoder is a similar function, where $g$ is permanently connected to logic 1. This yields a 1-of-2 decoder (1:2 decoder). This means only one output is logic 1 at a time.
![[DecoderExample.png]]
Here, $x=1, y=z=0$ would enable system 1 (an input of $001$, read from z->x)

Decoders can be used output combinational logic.
![[DecoderExample2.png]]
#### ROM
ROM is a data storage device that is:
- usually written into once
- read at will
- essentially a lookup table where a group of input lines specifies the address of locations holding words
e.g. if $n=4$, then ROM has $2^4=16$ possible locations. If $m=4$, then each location can store a 4-bit word. Therefore the total number of bits stored is $m\times2^n=64$.

ROM can be used to act as combinational logic. Storing the minterms in appropriate memory locations means no logic simplification is required and multiple Boolean expressions can be implemented. This is reasonable efficient if lots of minterms need to be generated.

However, ROM can be quite inefficient with only a few non-zero entries, as the number of minterms to be implemented is quite small.

### Programmable Logic Arrays
In a PLA, only the required minterms are generated using a separate AND plane. The outputs from this plane are ORed together in a separate OR plane to produce the final output.
![[BasicPLA.png]]
A modified structure known as Programmable Array Logic does not have a programmable OR array and so outputs from the AND array cannot be shared among the OR gates to give the final outputs.
![[BasicPAL.png]]