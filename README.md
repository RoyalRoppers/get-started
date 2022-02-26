# CTF: getting started

This is a document with tips for how to get started with CTFs.

## What is CTF?
CTF or Capture The Flag is a form of IT-security competition played in teams.
There are two main formats: Jeopardy and Attack-Defense. Jeopardy is the most
common format. In a Jeopardy CTF you are given a bunch of challenges in
different categories. You solve a challenge by finding a flag, which is just a 
text string with some given format (example: ctf{l33t_sp34k_h3r3}). Submitting 
the flag to the competition platform gives points. The team with the most points
win.

In Attack-Defense (AD) CTFs, teams are given access to some server in a network 
which they must defend against other teams and use as a platform to attack other
teams.

In Jeopardy style CTFs there are several common categories of challenges. Here 
are the main ones:

### Web
In web challenges you are tasked with attacking web applications. These kinds of
challenges are everything from server side attacks such as Local File Inclusion
(LFI), SQL Injection (SQLi), business logic bugs, IDOR, etc. to client side bugs
such as Cross Site Scripting (XSS), Cross Site Request Forgery (CSRF), etc. The
web applications you are up against can be written in many different languages:
PHP, Python, JavaScript, Java, Ruby, Golang, etc.

### Reversing
Most often you are given a binary executable compiled from C-code. With only the
binary, no source, you are tasked with understanding the program by reading its
assembly code. Your task is to figure out what the correct input is to the
program. Many times the program is structured in a way that the flag you seek is
the only correct input. Other times you must figure out a password, which when
submitted to the program will unlock and give you the flag.

### Pwn
Pwn, or Binary Exploitation is a category where you take advantage of memory 
corruption vulnerabilities in programs which handle their own memory such as C
or C++. Here you will run into vulnerabilities such as buffer overflows, heap 
corruption, return oriented program (ROP) and much more.

### Cryptography
You can divide cryptography into some broad categories. There is classic
cryptography (WW2 and earlier) where you should attack ciphers such as: Caesar
cipher, Vigenere cipher, etc. More interesting is modern cryptography which again
can be divided into symmetric and asymmetric (public key) cryptography. People
might be scared of cryptography because it contains math. Don't be scared, it's 
only when you get to public key cryptography when math comes into the picture.

### Forensics
In the real world, forensics is when you investigate evidence material after 
an incident to try and figure out how an attacker got access to your network, for 
example. In the CTF world it is partly that, but also a lot of challenges related
to broken and hidden files. Network analysis with packet captures fall into this 
category.

### Misc
Anything goes!

## How do I learn?
There is a ton of material online for learning about CTFs and about the different
categories. One way is to go through a bunch of different kinds of vulnerabilites,
one by one and learning how they work. There are many good YouTube channels as well. Here is a list of a bunch of security creators: https://securitycreators.video/ Here 
is a sample of some of my favorites:

- [LiveOverflow](https://www.youtube.com/c/LiveOverflow)
- [Gynvael](https://www.youtube.com/user/GynvaelEN)
- [IppSec](https://www.youtube.com/channel/UCa6eh7gCkpPo5XXUDfygQQA)

## Where do i practice?
Actually solving CTF problems is the best way to learn about CTFs. Make sure to
Google **a lot** as soon as there is something you get stuck on or don't
understand.

- [PicoCTF](https://www.picoctf.org/)
- https://github.com/zardus/wargame-nexus

## Basic Tools
These are tools that are used often in CTFs. There are definitely more specialized tools for different purposes out there, but these are a couple to get you started. (You can also find more [here](https://gist.github.com/ZetaTwo/40976c9ed8b9abb81e44c872b3a68551).)

### Number 1 tool: Text Editor
You will be reading and writing text files a lot. So you need a text editor. Here
are some options:

- [VSCode](https://code.visualstudio.com/)
- [Sublime Text](https://www.sublimetext.com/)

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

Disassemblers are good for static analysis, but if you want to investigate the
binary while it is running (dynamic analysis), you are going to need a debugger:

- gdb: For linux.
- [GEF](https://gef.readthedocs.io/en/master/): Enhancement to make gdb more useful (and beautiful). ([pwndbg](https://github.com/pwndbg/pwndbg) also exists)
- [x86dbg](https://x64dbg.com/): For windows.

There are also a couple other command line tools that are useful for looking at 
binaries:

- strace: Shows you which system calls a binary makes.
- ltrace: Shows you which libc calls a binary makes.
- objdump: Multitool. Can disassemble a binary.
- strigs: Shows all ASCII strings in the binary.

### PWN
When you need to build a ROP chain, you can use any of the following tools to
find gadgets:
- [rp++](https://github.com/0vercl0k/rp): General purpose gadget finder ([Ropper](https://github.com/sashs/ropper) and [ROPgadget](http://shell-storm.org/project/ROPgadget/) also exist).
- [one_gadget](https://github.com/david942j/one_gadget): Finds you a /bin/sh gadget at once.

Finding libc based on libc function offsets:
- https://libc.blukat.me/
- https://github.com/niklasb/libc-database
- https://libc.rip/

### Web

- [Burp suite](https://portswigger.net/burp): Web proxy, very good tool.
- [Wappalyzer](https://www.wappalyzer.com/): Browser extension which gives a quick glance at what a website is built with.
- [ngrok](https://ngrok.com/): Get a temporary domain for a local service.

### Cryptography

- [quipqiup](https://quipqiup.com/): A solver of English substitution ciphers.

### Steganography

- [Stegsolve](http://www.caesum.com/handbook/Stegsolve.jar): Multitool

### Forensics

- binwalk: Find hidden files within files.
- foremost: Like binwalk.
- [010editor (free trial)](https://www.sweetscape.com/010editor/): Great hex editor for investigating file formats. Shows the structure of the file.
- [kaitai web IDE](https://ide.kaitai.io/): Similar to 010editor.

### Network analysis

- [Wireshark](https://www.wireshark.org/)

### Misc

- [Cyberchef](https://gchq.github.io/CyberChef/): Super multitool!
