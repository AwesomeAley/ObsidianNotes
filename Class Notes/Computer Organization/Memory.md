Types of RAM Memory
- Dynamic Ram (DRAM)
- Static RAM (SRAM)
	- Flip flops
	- registers
	- shift registers
- Phase - Change Memory (PRAM)


### Dynamic RAM
- Can store information for only a few milliseconds 
- must be updated: rewriting data is called 'refreshing' (SRAM doesn't need refreshing)
- RAM memory is lost if electrical power is removed
- data read out is non destructive
- data can be stored, read, changed, and erased (very similar to SRAM functionality)

### ROM Memory
- Read only memory - non-volatile
	-information not lost when electrical power is removed
	some are erasable, but not the same as volatile
- Can be randomly accessed (similar in that respect to RAM)
- Data can be read out non-destructively

### ROM
- Permanently store patterns of bits
	- - instructions (micro-code: tell what to do when get input from the outside world)
	- data
- Change ROM: re-purpose CPU: calculator, children's toy, traffic light, electronic scale
- Can store data... but data can be thought of as "universal combinational logic"

### Remember NAND Gate
- ROM can be reprogrammed to imitate a logic gate
- first, lay out the NAND ROM gate on a matrix (ROM and RAM laid out in grids)
- output lines with a diode are logical 1
- output lines without a diode are a logical 0
-
##### ROM Application
7 segment display
- truth table is ROM layout
- much easier to program than logic gate method
- cant store ten 7-bit word or 7x10 bits = 70 bits
- 2^70 combinations of 0s and 1s