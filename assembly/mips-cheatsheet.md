## MIPS Cheat Sheet

### R-Type (Registers)
**Math**<br/>
add $1, $2, $3\t $1 = $2 + $3<br/>
sub $1, $2, $3\t $1 = $2 - $3<br/>
mult $1, $2, $3\t $1 = $2 x $3<br/>
div $1, $2, $3\t $1 = $2 / $3

**Bitwise**<br/>
and $1, $2, $3\t $1 = $2 AND $3<br/>
or $1, $2, $3\t $1 = $2 OR $3<br/>
xor $1, $2, $3\t $1 = $2 XOR $3<br/>
nor $1, $2, $3\t $1 = $2 NOR $3

**Shifting**<br/>
sll $1, $2, shamt\t $1 = $2 << shamt (shift left logical)<br/>
srl $1, $2, shamt\t $1 = $2 >> shamt (shift right logical)

### I-Type (Immediate)
**Branching**<br/>
beq $1, $2, imm\t if ($1 = $2) branch to imm<br/>
bne $1, $2, imm\t if ($1 != $2) branch to imm<br/>
blez $1, $2, imm\t if ($1 <= $2) branch to imm<br/>
bgtz $1, $2, imm\t if ($1 >= $2) branch to imm

**Math**<br/>
addi $1, $2, imm\t $1 = $2 + imm

**Bitwise**<br/>
andi $1, $2, imm\t $1 = $2 AND imm<br/>
ori $1, $2, imm\t $1 = $2 OR imm<br/>
xori $1, $2, imm\t $1 = $2 XOR imm

### J-Type (Jump)
j address\t (jump to address)<br/>
jal address\t (jump to address but save my current location)
