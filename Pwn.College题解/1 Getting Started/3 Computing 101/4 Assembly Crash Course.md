# 1.set-register

# 2.add-to-register

# 3.set-multiple-registers

```
.intel_syntax noprefix
.global _start
_start:
mov rsp, 0x31337
mov r12, 0xCAFED00D1337BEEF
mov rax, 0x1337
```



```sh
hacker@assembly-crash-course~set-multiple-registers:~$ touch asm.s
hacker@assembly-crash-course~set-multiple-registers:~$ vim asm.s 
hacker@assembly-crash-course~set-multiple-registers:~$ cat asm.s 
.intel_syntax noprefix
.global _start
_start:
mov rsp, 0x31337
mov r12, 0xCAFED00D1337BEEF
mov rax, 0x1337
hacker@assembly-crash-course~set-multiple-registers:~$ as -o ./asm.o ./asm.s && ld -o ./asm ./asm.o
hacker@assembly-crash-course~set-multiple-registers:~$ /challenge/run ./asm

In this level you will be working with registers. You will be asked to modify
or read from registers.


In this level you will work with multiple registers. Please set the following:
  rax = 0x1337
  r12 = 0xCAFED00D1337BEEF
  rsp = 0x31337

Extracting binary code from provided ELF file...
Executing your code...
---------------- CODE ----------------
0x400000:       mov     rsp, 0x31337
0x400007:       movabs  r12, 0xcafed00d1337beef
0x400011:       mov     rax, 0x1337
--------------------------------------
pwn.college{Er07kIBjA1L67DnEUVRRfHEePuF.QXwEDOzwCO5IzW}

hacker@assembly-crash-course~set-multiple-registers:~$ 
```



# 4.linear-equation-registers

# 5.integer-division

# 6.modulo-operation 

# 7.efficient-modulo

# 8.set-upper-byte

```
asm(code ,arch = 'amd64',os = 'linux')

```



```sh
hacker@assembly-crash-course~set-upper-byte:~$ /challenge/run 

In this level you will be working with registers. You will be asked to modify
or read from registers.

We will now set some values in memory dynamically before each run. On each run
the values will change. This means you will need to do some type of formulaic
operation with registers. We will tell you which registers are set beforehand
and where you should put the result. In most cases, its rax.


Another cool concept in x86 is the ability to independently access to lower register bytes.

Each register in x86_64 is 64 bits in size, and in the previous levels we have accessed
the full register using rax, rdi or rsi.

We can also access the lower bytes of each register using different register names.

For example the lower 32 bits of rax can be accessed using eax, the lower 16 bits using ax,
the lower 8 bits using al.

MSB                                    LSB
+----------------------------------------+
|                   rax                  |
+--------------------+-------------------+
                     |        eax        |
                     +---------+---------+
                               |   ax    |
                               +----+----+
                               | ah | al |
                               +----+----+

Lower register bytes access is applicable to almost all registers.

Using only one move instruction, please set the upper 8 bits of the ax register to 0x42.

We will now set the following in preparation for your code:
  rax = 0xe80c1bf48e260060

You ran me without an argument. You can re-run with `/challenge/run /path/to/your/elf` to input an ELF file, or just give me your assembled and extracted code in bytes (up to 0x1000 bytes): 
^Chacker@assembly-crash-course~set-upper-byte:~$ vim asm.s 
hacker@assembly-crash-course~set-upper-byte:~$ cat asm.s 
mov ah, 0x42
^[[Ahacker@assembly-crash-course~set-upper-byte:~$ cat asm.s 
mov ah, 0x42
hacker@assembly-crash-course~set-upper-byte:~$ as -o ./asm.o ./asm.s && ld -o ./asm ./asm.o
./asm.s: Assembler messages:
./asm.s:1: Error: operand size mismatch for `mov'
hacker@assembly-crash-course~set-upper-byte:~$ vim asm.s 
^[[Ahacker@assembly-crash-course~set-upper-byte:~$ cat asm.s 
mov rax, 0x4200
hacker@assembly-crash-course~set-upper-byte:~$ as -o ./asm.o ./asm.s && ld -o ./asm ./asm.o
./asm.s: Assembler messages:
./asm.s:1: Error: operand size mismatch for `mov'
hacker@assembly-crash-course~set-upper-byte:~$ vim asm.s 
hacker@assembly-crash-course~set-upper-byte:~$ as -o ./asm.o ./asm.s && ld -o ./asm ./asm.o
./asm.s: Assembler messages:
./asm.s:1: Error: operand size mismatch for `mov'
hacker@assembly-crash-course~set-upper-byte:~$ vim asm.s 
hacker@assembly-crash-course~set-upper-byte:~$ as -o ./asm.o ./asm.s && ld -o ./asm ./asm.o
./asm.s: Assembler messages:
./asm.s:1: Error: operand size mismatch for `mov'
hacker@assembly-crash-course~set-upper-byte:~$ ls
111  222  998  asm  asm.s  core  elf  elf.o  elf.s  foriso  lost+found  my_command  past  server3  server3.o  server3.s  x.sh
hacker@assembly-crash-course~set-upper-byte:~$ strace ./asm
execve("./asm", ["./asm"], 0x7ffca6258160 /* 23 vars */) = 0
--- SIGSEGV {si_signo=SIGSEGV, si_code=SEGV_MAPERR, si_addr=0x1337} ---
+++ killed by SIGSEGV (core dumped) +++
Segmentation fault
hacker@assembly-crash-course~set-upper-byte:~$ vim asm.s 
hacker@assembly-crash-course~set-upper-byte:~$ as -o ./asm.o ./asm.s
./asm.s: Assembler messages:
./asm.s:1: Error: operand size mismatch for `mov'
hacker@assembly-crash-course~set-upper-byte:~$ /challenge/run 

In this level you will be working with registers. You will be asked to modify
or read from registers.

We will now set some values in memory dynamically before each run. On each run
the values will change. This means you will need to do some type of formulaic
operation with registers. We will tell you which registers are set beforehand
and where you should put the result. In most cases, its rax.


Another cool concept in x86 is the ability to independently access to lower register bytes.

Each register in x86_64 is 64 bits in size, and in the previous levels we have accessed
the full register using rax, rdi or rsi.

We can also access the lower bytes of each register using different register names.

For example the lower 32 bits of rax can be accessed using eax, the lower 16 bits using ax,
the lower 8 bits using al.

MSB                                    LSB
+----------------------------------------+
|                   rax                  |
+--------------------+-------------------+
                     |        eax        |
                     +---------+---------+
                               |   ax    |
                               +----+----+
                               | ah | al |
                               +----+----+

Lower register bytes access is applicable to almost all registers.

Using only one move instruction, please set the upper 8 bits of the ax register to 0x42.

We will now set the following in preparation for your code:
  rax = 0xf89d0bc2913300e7

You ran me without an argument. You can re-run with `/challenge/run /path/to/your/elf` to input an ELF file, or just give me your assembled and extracted code in bytes (up to 0x1000 bytes): 
mov ah, 0x42

WARNING: It looks like your input might not be assembled binary
code, but assembly source code. This challenge needs the
raw binary assembled code as input.

Executing your code...
---------------- CODE ----------------
0x400000:       insd    dword ptr [rdi], dx
0x400001:       outsd   dx, dword ptr [rsi]
0x400002:       jbe     0x400024
--------------------------------------

ERROR: fail: this instruction is not allowed: insd
+--------------------------------------------------------------------------------+
| Registers                                                                      |
+-------+----------------------+-------+----------------------+------------------+
|  rax  |  0xf89d0bc2913300e7  |  rbx  |  0x0000000000000000  |                  |
|  rcx  |  0x0000000000000000  |  rdx  |  0x0000000000000000  |                  |
|  rsi  |  0x0000000000000000  |  rdi  |  0x0000000000000000  |                  |
|  rbp  |  0x0000000000000000  |  rsp  |  0x00007fffff200000  |                  |
|  r8   |  0x0000000000000000  |  r9   |  0x0000000000000000  |                  |
|  r10  |  0x0000000000000000  |  r11  |  0x0000000000000000  |                  |
|  r12  |  0x0000000000000000  |  r13  |  0x0000000000000000  |                  |
|  r14  |  0x0000000000000000  |  r15  |  0x0000000000000000  |                  |
|  rip  |  0x0000000000400000  |       |                      |                  |
+---------------------------------+-------------------------+--------------------+
| Stack location                  | Data (bytes)            | Data (LE int)      |
+---------------------------------+-------------------------+--------------------+
+---------------------------------+-------------------------+--------------------+
| Memory location                 | Data (bytes)            | Data (LE int)      |
+---------------------------------+-------------------------+--------------------+
|    0x0000000000404000 (+0x0000) | 00 00 00 00 00 00 00 00 | 0x0000000000000000 |
|    0x0000000000404008 (+0x0008) | 00 00 00 00 00 00 00 00 | 0x0000000000000000 |
|    0x0000000000404010 (+0x0010) | 00 00 00 00 00 00 00 00 | 0x0000000000000000 |
|    0x0000000000404018 (+0x0018) | 00 00 00 00 00 00 00 00 | 0x0000000000000000 |
+---------------------------------+-------------------------+--------------------+
hacker@assembly-crash-course~set-upper-byte:~$ ipython
Python 3.11.9 (main, Apr  2 2024, 08:25:04) [GCC 13.2.0]
Type 'copyright', 'credits' or 'license' for more information
IPython 8.24.0 -- An enhanced Interactive Python. Type '?' for help.

In [1]: from pwn import *

In [2]: asm = "mov ah, 0x42"

In [3]: payload = asm(code ,arch = 'amd64',os = 'linux')
---------------------------------------------------------------------------
NameError                                 Traceback (most recent call last)
Cell In[3], line 1
----> 1 payload = asm(code ,arch = 'amd64',os = 'linux')

NameError: name 'code' is not defined

In [4]: payload = asm(asm ,arch = 'amd64',os = 'linux')
---------------------------------------------------------------------------
TypeError                                 Traceback (most recent call last)
Cell In[4], line 1
----> 1 payload = asm(asm ,arch = 'amd64',os = 'linux')

TypeError: 'str' object is not callable

In [5]: asm = 'mov ah, 0x42'

In [6]: payload = asm(asm ,arch = 'amd64',os = 'linux')
---------------------------------------------------------------------------
TypeError                                 Traceback (most recent call last)
Cell In[6], line 1
----> 1 payload = asm(asm ,arch = 'amd64',os = 'linux')

TypeError: 'str' object is not callable

In [7]: payload = asm("mov ah, 0x42",arch = 'amd64',os = 'linux')
---------------------------------------------------------------------------
TypeError                                 Traceback (most recent call last)
Cell In[7], line 1
----> 1 payload = asm("mov ah, 0x42",arch = 'amd64',os = 'linux')

TypeError: 'str' object is not callable

In [8]: payload = asm('mov ah, 0x42',arch = 'amd64',os = 'linux')
---------------------------------------------------------------------------
TypeError                                 Traceback (most recent call last)
Cell In[8], line 1
----> 1 payload = asm('mov ah, 0x42',arch = 'amd64',os = 'linux')

TypeError: 'str' object is not callable

In [9]: exit()
hacker@assembly-crash-course~set-upper-byte:~$ ipython
Python 3.11.9 (main, Apr  2 2024, 08:25:04) [GCC 13.2.0]
Type 'copyright', 'credits' or 'license' for more information
IPython 8.24.0 -- An enhanced Interactive Python. Type '?' for help.

In [1]: from pwn import *

In [2]: code = 'mov ah, 0x42'

In [3]: payload = asm('mov ah, 0x42',arch = 'amd64',os = 'linux')

In [4]: p=process("/challenge/run")
[x] Starting local process '/challenge/run'
[+] Starting local process '/challenge/run': pid 5011

In [5]: p.send(payload)

In [6]: p.interactive()
[*] Switching to interactive mode
[*] Process '/challenge/run' stopped with exit code 0 (pid 5011)

In this level you will be working with registers. You will be asked to modify
or read from registers.

We will now set some values in memory dynamically before each run. On each run
the values will change. This means you will need to do some type of formulaic
operation with registers. We will tell you which registers are set beforehand
and where you should put the result. In most cases, its rax.


Another cool concept in x86 is the ability to independently access to lower register bytes.

Each register in x86_64 is 64 bits in size, and in the previous levels we have accessed
the full register using rax, rdi or rsi.

We can also access the lower bytes of each register using different register names.

For example the lower 32 bits of rax can be accessed using eax, the lower 16 bits using ax,
the lower 8 bits using al.

MSB                                    LSB
+----------------------------------------+
|                   rax                  |
+--------------------+-------------------+
                     |        eax        |
                     +---------+---------+
                               |   ax    |
                               +----+----+
                               | ah | al |
                               +----+----+

Lower register bytes access is applicable to almost all registers.

Using only one move instruction, please set the upper 8 bits of the ax register to 0x42.

We will now set the following in preparation for your code:
  rax = 0xdaea1002ac860020

You ran me without an argument. You can re-run with `/challenge/run /path/to/your/elf` to input an ELF file, or just give me your assembled and extracted code in bytes (up to 0x1000 bytes): 
Executing your code...
---------------- CODE ----------------
0x400000:       mov     ah, 0x42
--------------------------------------
pwn.college{IN-OGnIbvtxCconhAImT-5YLfEJ.QXxEDOzwCO5IzW}

[*] Got EOF while reading in interactive
```



# 9.byte-extraction

# 10.bitwise-and

# 11.check-even

# 12.memory-increment

# 13.memory-read

```sh
hacker@assembly-crash-course~memory-read:~$ ipython
Python 3.11.9 (main, Apr  2 2024, 08:25:04) [GCC 13.2.0]
Type 'copyright', 'credits' or 'license' for more information
IPython 8.24.0 -- An enhanced Interactive Python. Type '?' for help.

In [1]: from pwn import *

In [2]: code ="
  Cell In[2], line 1
    code ="
          ^
SyntaxError: unterminated string literal (detected at line 1)


In [3]: code ="
  Cell In[3], line 1
    code ="
          ^
SyntaxError: unterminated string literal (detected at line 1)


In [4]: code = '
  Cell In[4], line 1
    code = '
           ^
SyntaxError: unterminated string literal (detected at line 1)


In [5]: code = '
  Cell In[5], line 1
    code = '
           ^
SyntaxError: unterminated string literal (detected at line 1)


In [6]: code = '''
   ...: mov rax, [0x404000]
   ...: '''

In [7]: payload = asm(code,arch = 'amd64',os = 'linux')

In [8]: p=process("/challenge/run")
[x] Starting local process '/challenge/run'
[+] Starting local process '/challenge/run': pid 1053

In [9]: p.send(payload)

In [10]: p.interactive()
[*] Switching to interactive mode
[*] Process '/challenge/run' stopped with exit code 0 (pid 1053)

We will now set some values in memory dynamically before each run. On each run
the values will change. This means you will need to do some type of formulaic
operation with registers. We will tell you which registers are set beforehand
and where you should put the result. In most cases, its rax.

In this level you will be working with memory. This will require you to read or write
to things stored linearly in memory. If you are confused, go look at the linear
addressing module in 'ike. You may also be asked to dereference things, possibly multiple
times, to things we dynamically put in memory for your use.


Up until now you have worked with registers as the only way for storing things, essentially
variables such as 'x' in math.

However, we can also store bytes into memory!

Recall that memory can be addressed, and each address contains something at that location.

Note that this is similar to addresses in real life!

As an example: the real address '699 S Mill Ave, Tempe, AZ
85281' maps to the 'ASU Brickyard'.

We would also say it points to 'ASU Brickyard'.

We can represent this like:
  ['699 S Mill Ave, Tempe, AZ 85281'] = 'ASU Brickyard'

The address is special because it is unique.

But that also does not mean other addresses can't point to the same thing (as someone can have multiple houses).

Memory is exactly the same!

For instance, the address in memory that your code is stored (when we take it from you) is 0x400000.

In x86 we can access the thing at a memory location, called dereferencing, like so:
  mov rax, [some_address]        <=>     Moves the thing at 'some_address' into rax

This also works with things in registers:
  mov rax, [rdi]         <=>     Moves the thing stored at the address of what rdi holds to rax

This works the same for writing to memory:
  mov [rax], rdi         <=>     Moves rdi to the address of what rax holds.

So if rax was 0xdeadbeef, then rdi would get stored at the address 0xdeadbeef:
  [0xdeadbeef] = rdi

Note: memory is linear, and in x86_64, it goes from 0 - 0xffffffffffffffff (yes, huge).

Please perform the following:
  Place the value stored at 0x404000 into rax

Make sure the value in rax is the original value stored at 0x404000.

We will now set the following in preparation for your code:
  [0x404000] = 0x19bb31

You ran me without an argument. You can re-run with `/challenge/run /path/to/your/elf` to input an ELF file, or just give me your assembled and extracted code in bytes (up to 0x1000 bytes): 
Executing your code...
---------------- CODE ----------------
0x400000:       mov     rax, qword ptr [0x404000]
--------------------------------------
pwn.college{83JwkX3bC7u72qOQcHI3HWsRMoj.QXyEDOzwCO5IzW}

[*] Got EOF while reading in interactive
```



# 14.memory-write



```sh
hacker@assembly-crash-course~memory-write:~$ ipython
Python 3.11.9 (main, Apr  2 2024, 08:25:04) [GCC 13.2.0]
Type 'copyright', 'credits' or 'license' for more information
IPython 8.24.0 -- An enhanced Interactive Python. Type '?' for help.

In [1]: from pwn import *

In [2]: code = '''
   ...: mov [404000], rax
   ...: '''

In [3]: payload = asm(code,arch = 'amd64',os = 'linux')

In [4]: p=process("/challenge/run")
[x] Starting local process '/challenge/run'
[+] Starting local process '/challenge/run': pid 626

In [5]: p.send(payload)

In [6]: p.interactive()
[*] Switching to interactive mode
[*] Process '/challenge/run' stopped with exit code 0 (pid 626)

We will now set some values in memory dynamically before each run. On each run
the values will change. This means you will need to do some type of formulaic
operation with registers. We will tell you which registers are set beforehand
and where you should put the result. In most cases, its rax.

In this level you will be working with memory. This will require you to read or write
to things stored linearly in memory. If you are confused, go look at the linear
addressing module in 'ike. You may also be asked to dereference things, possibly multiple
times, to things we dynamically put in memory for your use.


Please perform the following:
  Place the value stored in rax to 0x404000

We will now set the following in preparation for your code:
  rax = 0x13bfcc

You ran me without an argument. You can re-run with `/challenge/run /path/to/your/elf` to input an ELF file, or just give me your assembled and extracted code in bytes (up to 0x1000 bytes): 
Executing your code...
---------------- CODE ----------------
0x400000:       mov     qword ptr [0x62a20], rax
--------------------------------------

Your program has crashed!
Invalid memory write (UC_ERR_WRITE_UNMAPPED)
This was the state of your program on crash:
+--------------------------------------------------------------------------------+
| Registers                                                                      |
+-------+----------------------+-------+----------------------+------------------+
|  rax  |  0x000000000013bfcc  |  rbx  |  0x0000000000000000  |                  |
|  rcx  |  0x0000000000000000  |  rdx  |  0x0000000000000000  |                  |
|  rsi  |  0x0000000000000000  |  rdi  |  0x0000000000000000  |                  |
|  rbp  |  0x0000000000000000  |  rsp  |  0x00007fffff200000  |                  |
|  r8   |  0x0000000000000000  |  r9   |  0x0000000000000000  |                  |
|  r10  |  0x0000000000000000  |  r11  |  0x0000000000000000  |                  |
|  r12  |  0x0000000000000000  |  r13  |  0x0000000000000000  |                  |
|  r14  |  0x0000000000000000  |  r15  |  0x0000000000000000  |                  |
|  rip  |  0x0000000000400000  |       |                      |                  |
+---------------------------------+-------------------------+--------------------+
| Stack location                  | Data (bytes)            | Data (LE int)      |
+---------------------------------+-------------------------+--------------------+
+---------------------------------+-------------------------+--------------------+
| Memory location                 | Data (bytes)            | Data (LE int)      |
+---------------------------------+-------------------------+--------------------+
|    0x0000000000404000 (+0x0000) | 00 00 00 00 00 00 00 00 | 0x0000000000000000 |
|    0x0000000000404008 (+0x0008) | 00 00 00 00 00 00 00 00 | 0x0000000000000000 |
|    0x0000000000404010 (+0x0010) | 00 00 00 00 00 00 00 00 | 0x0000000000000000 |
|    0x0000000000404018 (+0x0018) | 00 00 00 00 00 00 00 00 | 0x0000000000000000 |
+---------------------------------+-------------------------+--------------------+
[*] Got EOF while reading in interactive
^[[A^C[*] Interrupted

In [7]: code = '''
   ...: mov [0x404000], rax
   ...: '''

In [8]: payload = asm(code,arch = 'amd64',os = 'linux')

In [9]: p=process("/challenge/run")
[x] Starting local process '/challenge/run'
[+] Starting local process '/challenge/run': pid 1190

In [10]: p.send(payload)

In [11]: p.interactive()
[*] Switching to interactive mode
[*] Process '/challenge/run' stopped with exit code 0 (pid 1190)

We will now set some values in memory dynamically before each run. On each run
the values will change. This means you will need to do some type of formulaic
operation with registers. We will tell you which registers are set beforehand
and where you should put the result. In most cases, its rax.

In this level you will be working with memory. This will require you to read or write
to things stored linearly in memory. If you are confused, go look at the linear
addressing module in 'ike. You may also be asked to dereference things, possibly multiple
times, to things we dynamically put in memory for your use.


Please perform the following:
  Place the value stored in rax to 0x404000

We will now set the following in preparation for your code:
  rax = 0x1cb030

You ran me without an argument. You can re-run with `/challenge/run /path/to/your/elf` to input an ELF file, or just give me your assembled and extracted code in bytes (up to 0x1000 bytes): 
Executing your code...
---------------- CODE ----------------
0x400000:       mov     qword ptr [0x404000], rax
--------------------------------------
pwn.college{wfSsIH9sUNkBmJpbl3by_MTA8sb.QXzEDOzwCO5IzW}

[*] Got EOF while reading in interactive

```



# 15.memory-size-access

# 16.byte-access



```sh
hacker@assembly-crash-course~byte-access:~$ ipython
fPython 3.11.9 (main, Apr  2 2024, 08:25:04) [GCC 13.2.0]
Type 'copyright', 'credits' or 'license' for more information
IPython 8.24.0 -- An enhanced Interactive Python. Type '?' for help.

In [1]: from pwn import *

In [2]: code = '''
   ...: xor rax, rax
   ...: mov eax, 0x404000
   ...: '''

In [3]: payload = asm(code,arch = 'amd64',os = 'linux')

In [4]: p=process("/challenge/run")
[x] Starting local process '/challenge/run'
[+] Starting local process '/challenge/run': pid 1267

In [5]: p.send(payload)

In [6]: p.interactive()
[*] Switching to interactive mode
[*] Process '/challenge/run' stopped with exit code 0 (pid 1267)

We will now set some values in memory dynamically before each run. On each run
the values will change. This means you will need to do some type of formulaic
operation with registers. We will tell you which registers are set beforehand
and where you should put the result. In most cases, its rax.

In this level you will be working with memory. This will require you to read or write
to things stored linearly in memory. If you are confused, go look at the linear
addressing module in 'ike. You may also be asked to dereference things, possibly multiple
times, to things we dynamically put in memory for your use.


Recall that registers in x86_64 are 64 bits wide, meaning they can store 64 bits.

Similarly, each memory location can be treated as a 64 bit value.

We refer to something that is 64 bits (8 bytes) as a quad word.

Here is the breakdown of the names of memory sizes:
  Quad Word   = 8 Bytes = 64 bits
  Double Word = 4 bytes = 32 bits
  Word        = 2 bytes = 16 bits
  Byte        = 1 byte  = 8 bits

In x86_64, you can access each of these sizes when dereferencing an address, just like using
bigger or smaller register accesses:
  mov al, [address]        <=>        moves the least significant byte from address to rax
  mov ax, [address]        <=>        moves the least significant word from address to rax
  mov eax, [address]       <=>        moves the least significant double word from address to rax
  mov rax, [address]       <=>        moves the full quad word from address to rax

Remember that moving into al does not fully clear the upper bytes.

Please perform the following:
  Set rax to the byte at 0x404000

We will now set the following in preparation for your code:
  [0x404000] = 0x12e6b2

You ran me without an argument. You can re-run with `/challenge/run /path/to/your/elf` to input an ELF file, or just give me your assembled and extracted code in bytes (up to 0x1000 bytes): 
Executing your code...
---------------- CODE ----------------
0x400000:       xor     rax, rax
0x400003:       mov     eax, 0x404000
--------------------------------------
Failed in the following way: rax expected to be 0xb2, however was 0x404000
[*] Got EOF while reading in interactive
^C[*] Interrupted

In [7]: code = '''
   ...: xor rax, rax
   ...: mov rax, [0x404000]
   ...: '''

In [8]: payload = asm(code,arch = 'amd64',os = 'linux')

In [9]: p=process("/challenge/run")
[x] Starting local process '/challenge/run'
[+] Starting local process '/challenge/run': pid 1718

In [10]: p.send(payload)

In [11]: p.interactive()
[*] Switching to interactive mode
[*] Process '/challenge/run' stopped with exit code 0 (pid 1718)

We will now set some values in memory dynamically before each run. On each run
the values will change. This means you will need to do some type of formulaic
operation with registers. We will tell you which registers are set beforehand
and where you should put the result. In most cases, its rax.

In this level you will be working with memory. This will require you to read or write
to things stored linearly in memory. If you are confused, go look at the linear
addressing module in 'ike. You may also be asked to dereference things, possibly multiple
times, to things we dynamically put in memory for your use.


Recall that registers in x86_64 are 64 bits wide, meaning they can store 64 bits.

Similarly, each memory location can be treated as a 64 bit value.

We refer to something that is 64 bits (8 bytes) as a quad word.

Here is the breakdown of the names of memory sizes:
  Quad Word   = 8 Bytes = 64 bits
  Double Word = 4 bytes = 32 bits
  Word        = 2 bytes = 16 bits
  Byte        = 1 byte  = 8 bits

In x86_64, you can access each of these sizes when dereferencing an address, just like using
bigger or smaller register accesses:
  mov al, [address]        <=>        moves the least significant byte from address to rax
  mov ax, [address]        <=>        moves the least significant word from address to rax
  mov eax, [address]       <=>        moves the least significant double word from address to rax
  mov rax, [address]       <=>        moves the full quad word from address to rax

Remember that moving into al does not fully clear the upper bytes.

Please perform the following:
  Set rax to the byte at 0x404000

We will now set the following in preparation for your code:
  [0x404000] = 0xf5673

You ran me without an argument. You can re-run with `/challenge/run /path/to/your/elf` to input an ELF file, or just give me your assembled and extracted code in bytes (up to 0x1000 bytes): 
Executing your code...
---------------- CODE ----------------
0x400000:       xor     rax, rax
0x400003:       mov     rax, qword ptr [0x404000]
--------------------------------------
Failed in the following way: rax expected to be 0x73, however was 0xf5673
[*] Got EOF while reading in interactive
^C[*] Interrupted

In [12]: code = '''
    ...: xor rax, rax
    ...: mov al, [0x404000]
    ...: '''

In [13]: payload = asm(code,arch = 'amd64',os = 'linux')

In [14]: p=process("/challenge/run")
[x] Starting local process '/challenge/run'
[+] Starting local process '/challenge/run': pid 2157

In [15]: p.send(payload)

In [16]: p.interactive()
[*] Switching to interactive mode
[*] Process '/challenge/run' stopped with exit code 0 (pid 2157)

We will now set some values in memory dynamically before each run. On each run
the values will change. This means you will need to do some type of formulaic
operation with registers. We will tell you which registers are set beforehand
and where you should put the result. In most cases, its rax.

In this level you will be working with memory. This will require you to read or write
to things stored linearly in memory. If you are confused, go look at the linear
addressing module in 'ike. You may also be asked to dereference things, possibly multiple
times, to things we dynamically put in memory for your use.


Recall that registers in x86_64 are 64 bits wide, meaning they can store 64 bits.

Similarly, each memory location can be treated as a 64 bit value.

We refer to something that is 64 bits (8 bytes) as a quad word.

Here is the breakdown of the names of memory sizes:
  Quad Word   = 8 Bytes = 64 bits
  Double Word = 4 bytes = 32 bits
  Word        = 2 bytes = 16 bits
  Byte        = 1 byte  = 8 bits

In x86_64, you can access each of these sizes when dereferencing an address, just like using
bigger or smaller register accesses:
  mov al, [address]        <=>        moves the least significant byte from address to rax
  mov ax, [address]        <=>        moves the least significant word from address to rax
  mov eax, [address]       <=>        moves the least significant double word from address to rax
  mov rax, [address]       <=>        moves the full quad word from address to rax

Remember that moving into al does not fully clear the upper bytes.

Please perform the following:
  Set rax to the byte at 0x404000

We will now set the following in preparation for your code:
  [0x404000] = 0x1b5bd0

You ran me without an argument. You can re-run with `/challenge/run /path/to/your/elf` to input an ELF file, or just give me your assembled and extracted code in bytes (up to 0x1000 bytes): 
Executing your code...
---------------- CODE ----------------
0x400000:       xor     rax, rax
0x400003:       mov     al, byte ptr [0x404000]
--------------------------------------
pwn.college{Iemy1XscL4Qohw-pVXz0X4IBD3i.QX0EDOzwCO5IzW}

[*] Got EOF while reading in interactive

```



# 17.little-endian-write

# 18.memory-sum

# 19.stack-subtraction

# 20.swap-stack-values

# 21.average-stack-vaiues

# 22.absolute-jump



```assembly
hacker@assembly-crash-course~absolute-jump:~$ vim ./asm.s 
hacker@assembly-crash-course~absolute-jump:~$ ipython
Python 3.11.9 (main, Apr  2 2024, 08:25:04) [GCC 13.2.0]
Type 'copyright', 'credits' or 'license' for more information
IPython 8.24.0 -- An enhanced Interactive Python. Type '?' for help.

In [1]: from pwn import *

In [2]: code = '''
   ...: mov rax, 0x403000
   ...: jmp rax
   ...: '''

In [3]: payload = asm(code,arch = 'amd64',os = 'linux')
p=
In [4]: payload = asm(code,arch = 'amd64',os = 'linux')

In [5]: p=process("/challenge/run")
[x] Starting local process '/challenge/run'
[+] Starting local process '/challenge/run': pid 1196

In [6]: p.send(payload)

In [7]: p.interactive()
[*] Switching to interactive mode
[*] Process '/challenge/run' stopped with exit code 0 (pid 1196)

We will now set some values in memory dynamically before each run. On each run
the values will change. This means you will need to do some type of formulaic
operation with registers. We will tell you which registers are set beforehand
and where you should put the result. In most cases, its rax.

In this level you will be working with control flow manipulation. This involves using instructions
to both indirectly and directly control the special register `rip`, the instruction pointer.
You will use instructions such as: jmp, call, cmp, and their alternatives to implement the requested behavior.


Earlier, you learned how to manipulate data in a pseudo-control way, but x86 gives us actual
instructions to manipulate control flow directly.

There are two major ways to manipulate control flow:
 through a jump;
 through a call.

In this level, you will work with jumps.

There are two types of jumps:
  Unconditional jumps
  Conditional jumps

Unconditional jumps always trigger and are not based on the results of earlier instructions.

As you know, memory locations can store data and instructions.

Your code will be stored at 0x4000e5 (this will change each run).

For all jumps, there are three types:
  Relative jumps: jump + or - the next instruction.
  Absolute jumps: jump to a specific address.
  Indirect jumps: jump to the memory address specified in a register.

In x86, absolute jumps (jump to a specific address) are accomplished by first putting the target address in a register reg, then doing jmp reg.

In this level we will ask you to do an absolute jump.

Perform the following:
  Jump to the absolute address 0x403000

We will now set the following in preparation for your code:
  Loading your given code at: 0x4000e5

You ran me without an argument. You can re-run with `/challenge/run /path/to/your/elf` to input an ELF file, or just give me your assembled and extracted code in bytes (up to 0x1000 bytes): 
Executing your code...
---------------- CODE ----------------
0x4000e5:       mov     rax, 0x403000
0x4000ec:       jmp     rax
--------------------------------------
pwn.college{sZ8c8I-ltc7WZOpEgSitAxZ-mHR.QX1EDOzwCO5IzW}

[*] Got EOF while reading in interactive
```



疑惑

> Anything that looks like just plain `jmp label` is relative.
>
> Absolute jumps look like
>
> - `jmp register`
> - `jmp [address]`
> - `jmp segment:absoluteaddr`
> - `jmp far [address]`
>
> Any far jump is absolute, any indirect jump is absolute, the combination (far, indirect) is therefore also absolute. Far jump only happen when necessary (you have to change `cs` and it's not a `call`). Indirect jumps are used for function pointers, branch tables (used in some cases for `switch` statements), dynamic dispatch (virtual methods) and maybe for imported functions (usually you call them, but maybe it's a tail call).
>
> from:https://stackoverflow.com/questions/31544052/how-can-i-tell-if-jump-is-absolute-or-relative





# 23.relative-jump



```sh
hacker@assembly-crash-course~relative-jump:~$ ipython
Python 3.11.9 (main, Apr  2 2024, 08:25:04) [GCC 13.2.0]
Type 'copyright', 'credits' or 'license' for more information
IPython 8.24.0 -- An enhanced Interactive Python. Type '?' for help.

In [1]: from pwn import *

In [2]: code = '''
   ...: jump aaa
   ...: .rept 0x51
   ...: nop
   ...: .endr
   ...: aaa:
   ...: mov rax, 1
   ...: '''

In [3]: payload = asm(code,arch = 'amd64',os = 'linux')
[ERROR] There was an error running ['/usr/bin/x86_64-linux-gnu-as', '-64', '-o', '/tmp/pwn-asm-4rdtxc5p/step2', '/tmp/pwn-asm-4rdtxc5p/step1']:
    It had the exitcode 1.
    It had this on stdout:
    /tmp/pwn-asm-4rdtxc5p/step1: Assembler messages:
    /tmp/pwn-asm-4rdtxc5p/step1:8: Error: no such instruction: `jump aaa'
    
[ERROR] An error occurred while assembling:
       1: .section .shellcode,"awx"
       2: .global _start
       3: .global __start
       4: _start:
       5: __start:
       6: .intel_syntax noprefix
       7: .p2align 0
       8: jump aaa
       9: .rept 0x51
      10: nop
      11: .endr
      12: aaa:
      13: mov rax, 1
    Traceback (most recent call last):
      File "/nix/store/axhfsaalsp089fd0ibnv9xrlsdmpmvzx-python3-3.11.9-env/lib/python3.11/site-packages/pwnlib/asm.py", line 713, in asm
        _run(assembler + ['-o', step2, step1])
      File "/nix/store/axhfsaalsp089fd0ibnv9xrlsdmpmvzx-python3-3.11.9-env/lib/python3.11/site-packages/pwnlib/asm.py", line 431, in _run
        log.error(msg, *args)
      File "/nix/store/axhfsaalsp089fd0ibnv9xrlsdmpmvzx-python3-3.11.9-env/lib/python3.11/site-packages/pwnlib/log.py", line 439, in error
        raise PwnlibException(message % args)
    pwnlib.exception.PwnlibException: There was an error running ['/usr/bin/x86_64-linux-gnu-as', '-64', '-o', '/tmp/pwn-asm-4rdtxc5p/step2', '/tmp/pwn-asm-4rdtxc5p/step1']:
    It had the exitcode 1.
    It had this on stdout:
    /tmp/pwn-asm-4rdtxc5p/step1: Assembler messages:
    /tmp/pwn-asm-4rdtxc5p/step1:8: Error: no such instruction: `jump aaa'
    
p---------------------------------------------------------------------------
PwnlibException                           Traceback (most recent call last)
Cell In[3], line 1
----> 1 payload = asm(code,arch = 'amd64',os = 'linux')

File /nix/store/axhfsaalsp089fd0ibnv9xrlsdmpmvzx-python3-3.11.9-env/lib/python3.11/site-packages/pwnlib/context/__init__.py:1581, in LocalContext.<locals>.setter(*a, **kw)
   1578 if arch in ('i386', 'amd64') and endian == 'big':
   1579     raise AttributeError("Invalid arch/endianness combination: %s/%s" % (arch, endian))
-> 1581 return function(*a, **kw)

File /nix/store/axhfsaalsp089fd0ibnv9xrlsdmpmvzx-python3-3.11.9-env/lib/python3.11/site-packages/pwnlib/asm.py:759, in asm(shellcode, vma, extract, shared)
    757 except Exception:
    758     lines = '\n'.join('%4i: %s' % (i+1,line) for (i,line) in enumerate(code.splitlines()))
--> 759     log.exception("An error occurred while assembling:\n%s" % lines)
    760 else:
    761     atexit.register(lambda: shutil.rmtree(tmpdir))

File /nix/store/axhfsaalsp089fd0ibnv9xrlsdmpmvzx-python3-3.11.9-env/lib/python3.11/site-packages/pwnlib/asm.py:713, in asm(shellcode, vma, extract, shared)
    710 with open(step1, 'w') as fd:
    711     fd.write(code)
--> 713 _run(assembler + ['-o', step2, step1])
    715 if not vma:
    716     shutil.copy(step2, step3)

File /nix/store/axhfsaalsp089fd0ibnv9xrlsdmpmvzx-python3-3.11.9-env/lib/python3.11/site-packages/pwnlib/asm.py:431, in _run(cmd, stdin)
    429         msg += 'It had this on stdout:\n%s\n'
    430         args += stderr,
--> 431     log.error(msg, *args)
    433 return stdout

File /nix/store/axhfsaalsp089fd0ibnv9xrlsdmpmvzx-python3-3.11.9-env/lib/python3.11/site-packages/pwnlib/log.py:439, in Logger.error(self, message, *args, **kwargs)
    432 """error(message, *args, **kwargs)
    433 
    434 To be called outside an exception handler.
    435 
    436 Logs an error message, then raises a ``PwnlibException``.
    437 """
    438 self._log(logging.ERROR, message, args, kwargs, 'error')
--> 439 raise PwnlibException(message % args)

PwnlibException: There was an error running ['/usr/bin/x86_64-linux-gnu-as', '-64', '-o', '/tmp/pwn-asm-4rdtxc5p/step2', '/tmp/pwn-asm-4rdtxc5p/step1']:
It had the exitcode 1.
It had this on stdout:
/tmp/pwn-asm-4rdtxc5p/step1: Assembler messages:
/tmp/pwn-asm-4rdtxc5p/step1:8: Error: no such instruction: `jump aaa'



In [4]: code = '''
   ...: jmp aaa
   ...: .rept 0x51
   ...: nop
   ...: .endr
   ...: aaa:
   ...: mov rax, 1
   ...: '''

In [5]: payload = asm(code,arch = 'amd64',os = 'linux')
p
In [6]: p=process("/challenge/run")
[x] Starting local process '/challenge/run'
[+] Starting local process '/challenge/run': pid 1590

In [7]: p.send(payload)

In [8]: p.interactive()
[*] Switching to interactive mode
[*] Process '/challenge/run' stopped with exit code 0 (pid 1590)

We will now set some values in memory dynamically before each run. On each run
the values will change. This means you will need to do some type of formulaic
operation with registers. We will tell you which registers are set beforehand
and where you should put the result. In most cases, its rax.

In this level you will be working with control flow manipulation. This involves using instructions
to both indirectly and directly control the special register `rip`, the instruction pointer.
You will use instructions such as: jmp, call, cmp, and their alternatives to implement the requested behavior.


Recall that for all jumps, there are three types:
  Relative jumps
  Absolute jumps
  Indirect jumps

In this level we will ask you to do a relative jump.

You will need to fill space in your code with something to make this relative jump possible.

We suggest using the `nop` instruction. It's 1 byte long and very predictable.

In fact, the as assembler that we're using has a handy .rept directive that you can use to
repeat assembly instructions some number of times:
  https://ftp.gnu.org/old-gnu/Manuals/gas-2.9.1/html_chapter/as_7.html

Useful instructions for this level:
  jmp (reg1 | addr | offset) ; nop

Hint: for the relative jump, lookup how to use `labels` in x86.

Using the above knowledge, perform the following:
  Make the first instruction in your code a jmp
  Make that jmp a relative jump to 0x51 bytes from the current position
  At the code location where the relative jump will redirect control flow set rax to 0x1

We will now set the following in preparation for your code:
  Loading your given code at: 0x4000e8

You ran me without an argument. You can re-run with `/challenge/run /path/to/your/elf` to input an ELF file, or just give me your assembled and extracted code in bytes (up to 0x1000 bytes): 
Executing your code...
---------------- CODE ----------------
0x4000e8:       jmp     0x40013b
0x4000ea:       nop   
0x4000eb:       nop   
0x4000ec:       nop   
0x4000ed:       nop   
0x4000ee:       nop   
0x4000ef:       nop   
0x4000f0:       nop   
0x4000f1:       nop   
0x4000f2:       nop   
0x4000f3:       nop   
0x4000f4:       nop   
0x4000f5:       nop   
0x4000f6:       nop   
0x4000f7:       nop   
0x4000f8:       nop   
0x4000f9:       nop   
0x4000fa:       nop   
0x4000fb:       nop   
0x4000fc:       nop   
0x4000fd:       nop   
0x4000fe:       nop   
0x4000ff:       nop   
0x400100:       nop   
0x400101:       nop   
0x400102:       nop   
0x400103:       nop   
0x400104:       nop   
0x400105:       nop   
0x400106:       nop   
0x400107:       nop   
0x400108:       nop   
0x400109:       nop   
0x40010a:       nop   
0x40010b:       nop   
0x40010c:       nop   
0x40010d:       nop   
0x40010e:       nop   
0x40010f:       nop   
0x400110:       nop   
0x400111:       nop   
0x400112:       nop   
0x400113:       nop   
0x400114:       nop   
0x400115:       nop   
0x400116:       nop   
0x400117:       nop   
0x400118:       nop   
0x400119:       nop   
0x40011a:       nop   
0x40011b:       nop   
0x40011c:       nop   
0x40011d:       nop   
0x40011e:       nop   
0x40011f:       nop   
0x400120:       nop   
0x400121:       nop   
0x400122:       nop   
0x400123:       nop   
0x400124:       nop   
0x400125:       nop   
0x400126:       nop   
0x400127:       nop   
0x400128:       nop   
0x400129:       nop   
0x40012a:       nop   
0x40012b:       nop   
0x40012c:       nop   
0x40012d:       nop   
0x40012e:       nop   
0x40012f:       nop   
0x400130:       nop   
0x400131:       nop   
0x400132:       nop   
0x400133:       nop   
0x400134:       nop   
0x400135:       nop   
0x400136:       nop   
0x400137:       nop   
0x400138:       nop   
0x400139:       nop   
0x40013a:       nop   
0x40013b:       mov     rax, 1
--------------------------------------
pwn.college{QclEbgQACJYdEpMMh7G3PymkA5D.QX2EDOzwCO5IzW}

[*] Got EOF while reading in interactive

```



# 24.jump-trampoline

# 25.conditional-jump

# 26.indirect-jump

# 27.average-loop

# 28.count-non-zero

# 29.string-lower

# 30.most-common-byte



```assembly
; setup the base of the stack as the current top
mov rbp, rsp
; move the stack 0x14 bytes (5 * 4) down
; acts as an allocation
sub rsp, 0xff
; assign list[2] = 1337
mov rax, src_addr

loop1:

mov 
; do more operations on the list ...
; restore the allocated space
mov rsp, rbp
ret
```

