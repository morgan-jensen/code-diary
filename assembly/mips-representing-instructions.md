# Representing Instructions in MIPS

## MIPS R-Format Instructions
| op     | rs     | rt     | rd     | shamt  | funct  | 
| :---:  | :---:  | :---:  | :---:  | :---:  | :---:  |
| 6 bits | 5 bits | 5 bits | 5 bits | 5 bits | 6 bits |

Instruction Fields:
* op: operation code (opcode)
* rs: first source register number
* rt: second source register number
* rd: destination register number
* shamt: shift amount (00000 for now)
* funct: function code (extends opcode)

Example:
| special | $s1   | $s2   | $t0   | 0     | add    |
| :---:   | :---: | :---: | :---: | :---: | :---:  | 
| 0       | 17    | 18    | 8     | 0     | 32     |
| 000000  | 10001 | 10010 | 01000 | 00000 | 100000 |

00000010001100100100000000100000 is the binary for the command: add $t0, $s1, $s2

## MIPS I-Format Instructions
| op     | rs     | rt     | constant or address |
| :---:  | :---:  | :---:  | :---:               |
| 6 bits | 5 bits | 5 bits | 16 bits             |

Instruction Fields:
* op: operation code (opcode)
* rs: source register number
* rt: target register number
* constant or address (the immediate)

## MIPS Branch Addressing
| op     | rs     | rt     | constant or address | 
|:---:   | :---:  | :---:  | :---:               |
| 6 bits | 5 bits | 5 bits | 16 bits             |  

Instruction Fields:
* op: operation code (opcode)
* rs: first register to compare
* rt: second register to compare
* constant or address to jump to if true

PC = Program Counter<br/>
PC-Relative Addressing:
* Target address = PC + offset x 4
* PC has already incremented by 4 by this time
	* Remember the PC already did PC += 4


## MIPS Jump Addressing
| op     | address |
| :---:  | :---:   |
| 6 bits | 26 bits |

Instuction Fields:
* op: operation code (opcode)
* address to jump to
