---
title: "Nand2tetris W4"
author: ""
type: ""
date: 2019-09-15T16:55:58+07:00
subtitle: "Machine Language Programming"
image: ""
tags: ["learn", "course", "nand", "assembly", "I/O", "register"]
draft: false
---

> Background
>
> Every hardware platform is designed to execute commands in a certain machine language, expressed using agreed-upon binary codes. Writing programs directly in binary code is a possible, yet unnecessary. Instead, we can write such programs using a low-level symbolic language, called assembly, and have them translated into binary code by a program called assembler.

### Machine Language

After making the gates and chips in previous 3 weeks, i had a chance to learn more about the machine language which is in binary form. Though i could have writen code directly in binary, it didn't make sense at all. For a learning purpose, the course provided Assembler tool which helps translate my low lever symbolic language into binary code.

### Registers and Memory

![registers-memory](/images/registers-memory.png)

- D: data register

- A: address / data register

- M: the current selected memory register M = RAM[A]

Another important thing i have learnt is the memory hierachy which involves different types of memories inside a computer. There are namely registers, a few of them stay inside the CPU, the cache memory, main memory and disk memory. The idea is the more memory capacity, the slower access time.

During the course, we will gradually build a computer named Hack computer, which is a 16-bit machine consisting of data memory RAM, instruction memory ROM, CPU and instruction bus/ data bus/ address bus.

There are 2 types of instructions: 16-bit A-instructions and 16-bit C-instructions.

- A-instructions

    Syntax: @value

    Semantics: Set the A register to value, or refering to a symbol

    Example: @17 // Set A to 17

- C-instructions

![c-instruction](/images/c-instruction.png)

### Memory Mapped Output

One of the best thing i enjoyed is how the computer interacts with input and output devices. It turns out that creating a specific reserved memory area for each device is a great invention. 

For example, the monitor is continuously refreshed from a memory map dedicated for output display. To control what to appear on the screen, we write programs to manipulate this screen memory map. 

The keyboard is an example for input device, which is a one 16-bit location in memory maniuplated by which key is pressed on the keyboard. A scan code of `75` appears in keyboard memory map if the `k` is pressed.

### Hack Programming

Important things to finish the project:

- Register and memory

- Branching, variables, iterations

- Pointer, output/input

### Projects

For the project in this week, i have to write 2 programs. The first is a simple multiplication of 2 values in RAM[0] and RAM[1], then store the output into RAM[2]. Because the Hack machine language doesn't support multiply or divide calculation, i must use basic summation arithmetic with branching and iterations to implement the required program.

The final program requires me to draw a black screen if a key is pressed and draw a black screen if the key is released. I learnt to use pointer and manipulate with screen memory map with scan code from keyboard memory map. It took me a few hours to finish and what a learning experience it was.

> Make everything as simple as possible, but not simpler.
>
> —Albert Einstein (1879–1955)

---

**Key concepts:** op codes, mnemonics, binary machine language, symbolic machine language, assembly, low-level arithmetic, logical, addressing, branching, and I/O commands, CPU emulation, low-level programming.

[More information][project04]

[project04]: https://www.nand2tetris.org/project04