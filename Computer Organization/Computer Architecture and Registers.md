
Computer architecture: uses Bus systems

Bus system: everything on the bus should receive the same information, but only one should switch on.

2 or more devices attempting to use the bus at the same time: BUS CONTENTION

#### Registers
If flip flops are among most important circuits, then registers are the most important applications
a circuit with more than one flip flop connected together is a register although this is an expensive way to hold bits.


#### Shift Registers

Made out of flip flops
![[Pasted image 20230927101749.png]]

**Advanced shift register** shifts left to right, can be used to store instructions and memory addresses, store results of computations, delay by x clock cycles, and convert serial stream of bits into parallel slice of bits

Shift registers produce a time delay, simplify combinational logic, convert serial data to parallel data, change the order of bits

**Counters** are another application of flip flops. These are used in watches, clocks, voltmeters, frequency counters, and computers.

These count up to 2^n ie: 2^4 gives 16 combinations. These can be both up and down counters.

Asynchronous counters: output of one triggers the next
synchronous counters: all change at the same time

Asynchronous Ripple Counter
slower than synchronous counter
- less reliable than synchronous counter (but cheaper, uses fewer gates)
- can make out of JK and any other type of flip flops
- counters can also be used as dividers
![[Pasted image 20230927103131.png]]

Synchronous Counter (Parallel counter)
Much faster than ripple counters, but also use a few more gates (makes it more expensive)
4-bit synchronous counter is a modulo 16 counter
can string any number of flip flops together to make larger counter

![[Pasted image 20230927103113.png]]

Counter Applications:
- clock or watch: take 30 pulses per second from oscillator chip and divide to 1 per second
- up and down counters
- timers
- digital tools - voltmeters, frequency counters, and dividers
- computers (many applications such as circuits)






