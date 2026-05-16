# MIPS Operations

## Arithmetic Operations
* Takes 3 operands
	* add $1, $2, $3
	* $1 = $2 + $3
* All arithmetic operations have this form

Example:<br/> 
	C-code: f = (g + h) - (i + j)<br/>
	MIPS: <br/>
	add t0, g, h (t0 = g + h)<br/>
	add t1, i, j (t1 = i + j)<br/>
	sub s0, t0, t1 (s0 = t0 - t1)<br/>

### Register Operands
* Arithmetic instructions use register operands
* MIPS HAS A 32 X 32-bit register file
	* Used for frequently accessed data
	* Numbered 0 to 31
	* 32-bit data called a "word"
* Assembler names
	* $t0, $t1, ..., $t9 for temp values
	* $s0, $s1, ..., $s7 for saved values

### Memory Operands
* Main memory used for composite data
	* Arrays, structs, dynamic data
* To apply arithmetic operations
	* Load values from memory into registers
	* Store result from register to memory
* Memory is byte addressed
	* Each address identifies an 8-bit byte
* Words are aligned in memory
	* Addresses must be multiples of 4
* MIPS is Big Endian
	* Most-significant byte at least address of a word (1, 2, 3, 4)
	* Little Endian: least-significant byte at least address (4, 3, 2, 1)

Example:<br/>
	C-code:	g = h + A[8] (g is in $s1, h is in $s2, base address of A is in $3)<br/>
	MIPS:<br/>
	lw $t0, 32($s3) - load A[8] into $t0 (32 is the offset of the 8th index of A, 8 * 4 = 32)<br/>
	add $s1, $s2, $t0 - s1 = s2 + A[8] <br/>

Example 2: <br/>
	C-code: A[12] = h + A[8]<br/>
	MIPS: <br/>
	lw $t0, 32($s3) - load word<br/>
	add $t0, $s2, $t0 - h + A[8]<br/>
	sw $t0, 48($s3) - A[12] = $t0 (Notice how sw is backwards from lw. In sw, the destination comes second.)

### Immediate Operands
* Constant data specified in an instruction
	* addi $s3, $s3, 4
* No subtract immediate instruction
	* Just use negative constant
	* addi $s2, $s1, -1

## Logical Operations
| Operation   | C         | Java     | MIPS      | 
| :---:       | :---:     | :---:    | :---:     |
| Shift Left  | <<        | <<       | sll       | 
| Shift Right | >>        | >>>      | srl       |
| AND         | &         | &        | and, andi | 
| OR          | \|        | \|       | or, ori   |
| NOT         | ~         | ~        | not       | 

* Shift Operations
	* shamt: how many positions to shift
	* Shift Left
		* Shift left and fill with 0 bits
		* sll by i bits multiplies by 2^i

* AND Operations
	* Useful to mask bits in a word
		* Select some bits, clear others to 0
		* and $t0, $t1, $t2

* OR Operations
	* Useful to include bits in a word
		* Set some bits to 1, leave others unchanged
		* or $t0, $t1, $t2

## Conditional Operations
* Branch to a labeled instruction if a condition is true
	* beq rs, rt, L1 (branch if rs = rt to L1)
	* bne rs, rt, L1 (branch if rs !- rt to L1)
	* j L1 (jump to L1 unconditionally)
