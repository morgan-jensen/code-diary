# Compiler Errors
Contained in this section are a list of compier errors I have gotten while working with C and how to fix them.

## Relocation truncated to fit R_x86_64_PC32 against symbol
This is an ELF relocation type used in ELF for x86\_64. It expresses that the location of the referenced data is computed based on a 
32-bit offset from the address related to the program counter.

Essentially the needed offsets are too large to fit in the provided 32 bits, meaing that you have defined an object that is larger 
than the compiler can accommodate. You are going beyond design limits.

To fix this error, find the object that is too big and shrink it to a usable size.

Example: 

```
struct LargeThing {
    // lots of stuff in here to make it big
}

struct LargeThing[INT_MAX];
```

This is the case in which I encountered the error. The struct was about 160 bytes, but `160 * INT_MAX` was too big for the compiler.

Solution found [here](https://stackoverflow.com/questions/57331990/c-compiling-relocation-truncated-to-fit-r-x86-64-pc32-against-symbol)

