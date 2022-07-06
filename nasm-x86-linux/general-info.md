# Registers
| 8-bit | 16-bit    | 32-bit    | 64-bit    |
| :---: | :---:     | :---:     | :---:     |
| al    | ax        | eax       | rax       |
| bl    | bx        | ebx       | rbx       |
| cl    | cx        | ecx       | rcx       |
| dl    | dx        | edx       | rdx       |
| sil   | si        | esi       | rsi       |
| dil   | di        | edi       | rdi       |
| bpl   | bp        | ebp       | rbp       |
| spl   | sp        | esp       | rsp       |
| r8b   | r8w       | r8d       | r8        |
| r9b   | r9w       | r9d       | r9        |
| r10b  | r10w      | r10d      | r10       |
| r11b  | r11w      | r11d      | r11       |
| r12b  | r12w      | r12d      | r12       |
| r13b  | r13w      | r13d      | r13       |
| r14b  | r14w      | r14d      | r14       |
| r15b  | r15w      | r15d      | r15       |


# System Calls
A system call, or syscall, is when a program requests a service from the kernel.

System calls will differ by operating system because of different kernels.

All syscalls have an ID associated with them. 

Syscalls also take arguments, meaning, a list of inputs.

## System call inputs by register:

| Argument  | Registers |
| :---:     | :---:     |
| ID        | rax       |
| 1         | rdi       |
| 2         | rsi       |
| 3         | rdx       |
| 4         | r10       |
| 5         | r8        |
| 6         | r9        |


# System Call List

\# = actual value (number) <br/>
$ = address

| syscall   | ID    | ARG1            | ARG2    | ARG3      |
| :---:     | :---: | :---:           | :---:   | :---:     | 
| sys_read  | 0     | #fileDescriptor | $buffer | #count    | 
| sys_write | 1     | #fileDescriptor | $buffer | #count    | 
| sys_open  | 2     | $fileName       | $buffer | #mode     | 
| sys_close | 3     | #fileDescriptor |         |           | 
| ...       | ...   | ...             | ...     | ...       | 
| pwritev2  | 328   | ...             | ...     | ...       |


# sys_write Example

| Argument Type     | Argument Description                                      | 
| :---:             | :---:                                                     | 
| File Descriptor   | 0 (std input) <br/> 1 (std output) <br/> 2 (std error)    | 
| Buffer            | Location of string to write                               | 
| Count             | Length of string                                          | 

| syscall   | rax   | rdi               | rsi       | rdx       |
| :---:     | :---: | :---:             | :---:     | :---:     |
| sys_write | 1     | #fileDescriptor   | $buffer   | #count    | 

Hello World: 
```
section .data
    text db "Hello, World!", 10 ; save double word (4 bytes) for "Hello, World!" + new line char (10)

section .text
    global _start
_start:
    mov rax, 1      ; move ID 1 into rax for sys_write
    mov rdi, 1      ; move 1 into rdi for std output
    mov rsi, text   ; move address of "Hello, World!" into rsi
    mov rds, 14     ; ask to print 14 chars
    syscall

    mov rax, 60     ; move ID 60 into rax for sys_exit
    xor rdi, rdi    ; set rdi to 0 (return 0 in c and c++) - xor is faster then mov
    syscall
```
| syscall   | rax   | rdi       | rsi           | rdx       |
| :---:     | :---: | :---:     | :---:         | :---:     |
| sys_write | 1     | 1         | ADDR (text)   | 14        | 

| syscall   | rax   | rdi        | rsi           | rdx       |
| :---:     | :---: | :---:      | :---:         | :---:     |
| sys_exit  | 60    | #errorCode |               |           | 


# Sections of x86
### .data
* Where all data is defined before compilation.
  
### .text
* Where the actual code goes.

### .bss
* Where data is allocated for future use.


# Labels
A label saves the address of the next instruction. Used to jump to.

```_start```
* Essential for all programs.
* Where the program begins (main method in other languages).
* If the linker cannot find "_start" it will throw an error.

```global``` 
* Used when you want the linker to be able to know the address of a label.
* Object file generated will contain a link to every label declared "global".
* In this case we have to declare "_start" as a global since it is required for the code to be properly linked.