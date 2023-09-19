# Reverse engineering / Assembly crash course

## Background

- Forward vs. reverse engineering
- Diagram with compilation, decompilation, assembling, disassembly
- Dynamic vs. static reversing

### Disassembly


### Decompilation


### Representing things with bytes


### Endianness


### Packing in Python


### Assembly


### Assembly syntax variations


### Assembly registers

- https://sandpile.org/x86/gpr.htm

### The stack


### Calling convetions


### Stripped vs. Non-stripped


### Dynamic vs. Static linking


## Methodology

### What to do first?


### Using GDB


### Ignoring the constant stuff


### Using Ghidra


## Tools

This section just lists tools and how to install them. For guidance on how
to use them, see the rest of the guide. The most basic tools are:

- `gdb` - a debugger
- `binutils` - contains `objdump`, `readelf`, `nm`, etc...
- `gcc` - contains `gcc` (c compiler), `ldd`, etc...

These can be installed with your package manager. Example: `apt install gdb
binutils gcc`. And you likely already have them installed.

You will also need a reverse engineering suite. This is kind of like a
large IDE, but for reverse engineering. They usually contain a disassembler,
a decompiler, and lots more. Here are some options:

- Ghidra - https://ghidra-sre.org/
- IDA Freeware - https://hex-rays.com/ida-free/
- Binary Ninja - https://binary.ninja/

Ghidra is completely free, while IDA and Binja are both commercial, but
offer demo/trial/free versions.

To make your `gdb` experience nicer (read: bearable), you can (need to)
install GEF (https://github.com/hugsy/gef).

For convenient scripting around binaries and process interaction, install
the `pwntools` library for python (`pip install pwntools`). This is a must
have for pwn and a nice-to-have for reversing. Here is some documentation
for how to use it: https://docs.pwntools.com/en/latest/intro.html

## Extras

### Nice Ghidra config


