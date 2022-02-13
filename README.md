# CTF: getting started

This is a document with tips for how to get started with CTFs.

## What is CTF?
...

### Web
...

### Reversing
...

### PWN
...

### Cryptography
...

### Forensics
...

### Misc
...

## Where do i practice?

- [PicoCTF](https://www.picoctf.org/)
- https://github.com/zardus/wargame-nexus

## Basic Tools
These are tools that are used often in CTFs. There are definitely more specialized tools for different purposes out there, but these are a couple to get you started. 

### Scripting
CTF players often use Python for scripting, you can certainly use other languages as well, but there is a lot of tooling in Python.

- [pwntools](https://pypi.org/project/pwntools/): Makes it easy to interact with challenges communicating over TCP (think nc/netcat). Is also indispensible for PWN challenges, as the name implies.
- [requests](https://pypi.org/project/requests/): Good for scripting interaction with web applications.
- [Pillow](https://pypi.org/project/Pillow/): For manipulating images.
- [pycryptodome](https://pypi.org/project/pycryptodome/): Contains many crypto algorithms.

### Binaries
The rev and PWN categories focus on analysing binaries. To do that you need a good disassembler/decompiler. A disassembler converts machine code into assembly and a decompiler converts machine back into C. You are gonna need to learn assembly anyways, so don't get scared by programs that don't have a decompiler. Here are some good options for disassemblers/decompilers:

- [IDA Freeware](https://hex-rays.com/ida-free/)
- [Ghidra](https://ghidra-sre.org/)
- [Binary Ninja](https://binary.ninja/)

There are also a couple other command line tools that are useful for looking at 
binaries:

- strace: Shows you which system calls a binary makes.
- ltrace: Shows you which libc calls a binary makes.
- objdump: Multitool. Can disassemble a binary.
- strigs: Shows all ASCII strings in the binary.

### PWN
When you need to build a ROP chain, you can use any of the following tools to
find gadgets:
- [ROPgadget](http://shell-storm.org/project/ROPgadget/): General purpose gadget finder. 
- [Ropper](https://github.com/sashs/ropper): General purpose gadget finder.
- [rp++](https://github.com/0vercl0k/rp): General purpose gadget finder.
- [one_gadget](https://github.com/david942j/one_gadget): Finds you a /bin/sh gadget at once.

Finding libc based on libc function offsets:
- https://libc.blukat.me/
- https://github.com/niklasb/libc-database
- https://libc.rip/

### Web

- [Burp suite](https://portswigger.net/burp): Web proxy, very good tool.
- [Wappalyzer](https://www.wappalyzer.com/): Browser extension which gives a quick glance at what a website is built with.
- [ngrok](https://ngrok.com/): Get a temporary domain for a local service.

### Steganography

- [Stegsolve](http://www.caesum.com/handbook/Stegsolve.jar): Multitool

### Forensics

- binwalk: Find hidden files within files.
- foremost: Like binwalk.
- [010editor (free trial)](https://www.sweetscape.com/010editor/): Great hex editor for investigating file formats. Shows the structure of the file.
- [kaitai web IDE](https://ide.kaitai.io/): Similar to 010editor.

### Misc

- [Cyberchef](https://gchq.github.io/CyberChef/): Super multitool!
