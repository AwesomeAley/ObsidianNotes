### Common Computer Architecture
![[Pasted image 20231018101809.png]]
##### Input:
Anything that sends inputs into the computer: (keyboard/terminal, voice, mouse, joystick, gyroscope, etc.) Common function is to convert analog (physical) data to digital data.

##### Output: 
The information that a computer sends out of it. Visualized via speakers, monitors, lights, printouts. Output devices are fairly simple, they send data often serially via output buffer to somewhere. Converts digital data to analog

##### Memory
- RAM Random access, read and write, volatile
- ROM Random access, read only, non-volatile
- Computer organization fact:
	- Usually, data and programs are stored in different areas of memory
	- A computer must have memory to qualify as a computer
Address space: How much memory that can be addressed via the bus

##### **CPU The central processing unit**
This is the most active part of the computer. The CPU (control and ALU and some registers). The CPU when on a single chip is called a microprocessor. When the entire computer is put on a single chip, is is called a Soc (System on a chip) The control section sends orders to the other parts of the machine.

Electronically rearrange the way its parts are interconnected
-Major systems: Input/output/CPU/Memory are connected to 'buses'
	- Bundles of wires or conduction paths on the circuit board
Kinds of buses: Address bus, control bus, and power bus

The lowest level computer language that you can program is **machine language** (stored as binary numbers)
Machine language instructions are made of micro-instructions (micro-code). Machine language instruction also known as macro-instruction

The CPU operates with the:
Fetch, Decode, Execute cycle:
	- Fetch next instruction
	- decode it (get micro-code instructions)
	- Execute it
	- Repeat cycle...
The computer is a giant state-machine with a clock

The PIP-1 is a hypothetical or instructional computer
- Bus-orientated
	Address/Data bus: bi --directional
		Binary address sent from input down to memory
		binary word sent from memory up to control
	Control bus: uni-directional
		carry micro code from control to other sections
	Power supply bus: not shown in diagrams