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

#### Buses
Bus information for the PIP instructional computer [[Pip Buses]]

### Pip-1 Microinstruction Sequencer
- When W is 1, data on bus is written to register
- When R is 1, register data read onto bus
- Source vs. destination
- No data is transferred unless a clock pulse arrives!
- Clock pulse must arrive AFTER control signals
	- Microinstruction sequencer delays clock pules to its control section by part of a clock cycle

#### Control Words
Each combination of input signals that can be applied to the 3 registers is a 'control word' You can make a truth table using each combination
For the three register: A, B, and C with the inputs depicted in the previous diagram: write, clock, read
Transfer data between register via a *shared* bus

#### Pip-1 Registers
MAR - Memory Address Register
- points to memory location in PROM
IR - Instruction Register
- Instruction to be decoded and executed
A Register (The Accumulator)
- Accumulator for arithmetic
B Register
- Working register
C Register (Output)
- Illuminates LED lamps on front panel
Registers are strings of flip flops! Static RAM

#### PIP-1 Input/Output
- Input is front panel switches
	- 16 x 8 switches for new machine language program (PROM)
	- START/STOP switches
- Output is front panel LED lights
	- C register - 8 lamps
	- Busy lamp
- Input/output is switches and lamps

#### Control
- PROM hold the machine language program (Instruction and Data)
	- PROM is an array of diodes connected to physical switches (can be re-programmed by user)
- Program Counter is a 4-bit binary counter - location in memory of current instruction
	- program counter is a string of flip flops
- Control is micro-sequencer and logic to orchestrate timing and sequences of micro-code in ROM
	- control is timer, micro-code in ROM, and logic

PROM VS ROM
- PROM is 'programable' It is the machine language program input on the front panel switch
- 
- PROM contains 4 to 16 line decoders (few to many)
- MAR is a 4 bit register that selects any of the 16 bytes stored in PROM
- Press START BUTTON: Program counter is reset to address 0000 (cold start)
- Release START BUTTON: Program Counter sends 0000 to MAR (when MAR/W is logical 1). When PROM/R receives logical 1 from CONTROL, bye select by MAR is written onto A/D bus (byte could be instruction of data)... then read into any section of PIP-1 as specified by control.

#### Example of Assembly Language Program

| Step | Mnemonic |    Op-Code | PRAD |
| ---- | -------- | --- | ---- |
| 0    | LDA      |  0001   | 0100 |
| 1    | ADD      |    0010 | 0101 |
| 2    | OUT      |    0101 | XXXX |
| 3    | HLT      |    0111 | XXXX |

