The PIP-1 is a hypothetical or instructional computer
- Bus-orientated
	Address/Data bus: bi --directional
		Binary address sent from input down to memory
		binary word sent from memory up to control
	Control bus: uni-directional
		carry micro code from control to other sections
	Power supply bus: not shown in diagrams

Keep it simple:
- 4 & 8 bit 'words' (4 bit bus)
- few instructions: addition and subtraction
- 3 general purpose registers: A (accumulator) B, and C
- Instruction Register and Memory Address Register
- Program counter
- INPUT, OUTPUT, ALU, CONTROL, PROM (programmable read only memory)
- Control bus, address/data bus

Pip 8 Instruction Set

| Mnemonic | Explanation      |
| --- | ------------------------- |
| LDA | Load the accumulator                          |
| ADD | PRAD byte plus A; into A  |
| SUB | A minus PRAD; into A      |
| JMP | PRAD byte into PC         |
| CLR | Clear A, B, C (0000 0000) |
| OUT | A into C                  |
| NOP | No operation              |
| HLT | Halt                      |

Bus information for the PIP instructional computer [[Pip Buses]]

Pip-1 Microinstruction Sequencer
- When W is 1, data on bus is written to register
- When R is 1, register data read onto bus
- Source vs. destination
- No data is transferred unless a clock pulse arrives!
- Clock pulse must arrive AFTER control signals
	- Microinstruction sequencer delays clock pules to its control section by part of a clock cycle

Control Words
Each combination of input signals that can be applied to the 3 registers is a 'control word' You can make a truth table using each combination
For the three register: A, B, and C with the inputs depicted in the previous diagram: write, clock, read
Transfer data between register via a *shared* bus