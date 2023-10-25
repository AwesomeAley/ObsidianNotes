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


