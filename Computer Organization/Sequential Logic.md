- Combination Logic Circuits: Have no memory when input is removed, and output is lost.
- Flip-flops: most basic sequel logic
- Store their state memory
#### Flip Flops
- Most basic: 2 crossed AND gates
- 2 outputs opposite of each other
- 2 state or logic circuits, (many flipflops make a multi stable)
- when changes states, it remains in that state even after momentary input signal changes! <- memory!

- Static RAM: Flip-Flops (4-6) transistors
- Dynamic RAM: Capacitors
- Flip-Flops more 'expensive' (more components, more space on chip) than dynamic RAM
- Registers, cache, etc, use SRAM, more expensive memory for inside CPU
- Dynamic Ram (DRAM) uses cheaper memory, but must be 'refreshed' many times (thousands) per second: slower, but cheaper... (less components, capacitor and a gate)

Introduction to Sequential Logic
- memory
- flip-flops
- timing
- shift registers
- counters
- synchronous
- asynchronous

##  RS Flip-Flop
#### RS Flip-Flop Truth Table

| S   | R   | Q   | Q'  |     | 
| --- | --- | --- | --- | --- |
| 0   | 0   | ?   | ?   |Disallowed     |
| 0   | 1   | 1   | 0   |Set     |
| 1   | 0   | 0   | 1   | Reset    |
| 1   | 1   | Q   | Q'  |No change     |


![[Pasted image 20230925102842.png]]


## D Flip Flop
Allows us to store 1 bit of data for 1 clock pulse
- looks like a clocked RS flip-flop with an inverter on the input
- inverter guarantees that R input is complement of S input
- "D" stands for data or delay

![[Pasted image 20230925103258.png]]


## JK Flip-Flop

- solves disallowed state of the RS flip-flop by permitting identical inputs
#### Truth Table
| J   | K   | Q   | Q'  |           |
| --- | --- | --- | --- | --------- |
| 0   | 0   | Q   | Q'  | no change |
| 0   | 1   | 0   | 1   |           |
| 1   | 0   | 1   | 0   |           |
| 1   | 1   | Q   | Q'  | Toggle    | 

![[Pasted image 20230925103540.png]]


## Toggle Flip-Flop

- When T is at logical 0, ignores clock pulse
- When T is at logical 1, Q and Q' cycle between 0 and 1
- Importance: Divides the incoming pulse by 2

![[Pasted image 20230925103756.png]]

The Q output has half the frequency of the incoming clock pulses


## Primary - Secondary Flip-Flips

- The glitch will go unnoticed because the glitch will happen before the falling edge of the clock


**Quiz/Test Review**
- What are the difference between RS, D, JK, and T flip flops
- What is the weakness of the RS flip flop
- What are the other names for the RS flip flop
- How do the D and JK flip flops solve the problem the RS flip flop has?
- What is special about the T flip flop
- Hod do you make a t flip flop
- What is a glitch? what is the solution?
  