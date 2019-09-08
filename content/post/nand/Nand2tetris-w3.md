---
title: "Nand2tetris Week3"
author: ""
type: ""
date: 2019-09-08T10:59:20+07:00
subtitle: "Memory & Hello Time"
image: ""
tags: ["learn", "course", "nand", "logic", "gate", "RAM", "memory"]
draft: false
---

> Background
>
> The computer's main memory, also called Random Access Memory, or RAM, is an addressable sequence of n-bit registers, each designed to hold an n-bit value. In this project you will gradually build a RAM unit. This involves two main issues: (i) how to use gate logic to store bits persistently, over time, and (ii) how to use gate logic to locate ("address") the memory register on which we wish to operate.

Well, this third week took me over a week to finally finish it. I have to priotize another learning for a side project at work, where my responsibility is to develop a front end app using [Google's UI toolkit flutter][flutter]. For this experience, you can read more in another post.

It turned out the idea of physical time and clock time took a litte while for me to fully comprehend. Unlike the combinational logic where the output is a pure function of the present input only, sequential logic output depends on the present input (optionally) and the history of the input (the memory part).

The heart of this memory effect is the chip called DFF (data flip-flops). This DFF is provided due to the limitation of the hardware simulator used in the course, and is the atom chip used to build other sequential chips. The idea is to combine the group of combinational logic and DFF chips to construct the register chip and later random access memory chips (RAM).

Notice the small triangular icon inside the DFF, this represents the memory effect of the sequential chips.

![seq-chip](/images/sequential-chip.png)

With this concept in my, i could write files for 1-bit register, multi-bit register, RAM8, RAM64, RAM512, RAM4K and RAM16K with little effort.

![RAM](/images/RAM.png)

The last chip, the most time-consuming, is Program Counter (PC). While playing around with the hdl code, i slowly grasp the idea of computer memory and of the usage of RAM. The PC is designed to support 3 operations:

- Reset: fetch the first instruction

- Next: fetch the next instruction

- Goto: fetch the instruction *n*

![PC](/images/PC.png)

Finishing on PC and all project codes passed test successfully, it felt like i would fly to the sky. Bring on week 4!

---

**Key concepts:** combinational vs sequential logic, clocks and cycles, flip-flops, registers, RAM units, counters.

[More information][project03]



[flutter]: https://flutter.dev/
[project03]: https://www.nand2tetris.org/project03