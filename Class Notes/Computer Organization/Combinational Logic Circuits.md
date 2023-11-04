Types of combinational [[Logic Gates]]
Sequential logic can be performed using [[Flip Flops]]

**Parity Checker**
- Catches most transmission errors (but not all)
- even or odd number of '1's
- extremely fast/efficient to preform error checking in hardware
- cheap and easy to do
- great fit for the XOR gate

**Half Adder**
- Perfect use of XOR gate: adds 2 binary bits

*Truth Table*

| A   | B   | S   |
| --- | --- | --- |
| 0   | 0   | 00   |
| 0   | 1   | 01   |
| 1   | 0   | 01   |
| 1   | 1   | 10   |


**Full Adder**
The FA can add 3 bits. It is made of two half adders plus an OR gate. The Full Adder has 2 inputs plus a carry input (for a total of 3 inputs). 

**Decoders**
Number systems can be thought of as codes. Transform binary numbers into more readable number systems:
- (few to many)
- Binary to octal
- BCD to decimal
- counter/alarm
- BCD to 7-segment display (LED)
Decoders use AND gates.

**Encoders**
- (Many to few)
- decimal, keypads -> binary, octal BDC
- made from OR gates

**Multiplexers**
- Data selector (many to one)
- many inputs to one output
- MUX used for stereo stuff

**Demultiplexers**
- one input to many outputs
- accessing memory
- like a selector switch

