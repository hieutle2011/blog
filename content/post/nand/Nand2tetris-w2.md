---
title: "Nand2tetris Week2"
author: ""
type: ""
date: 2019-08-26T10:32:12+07:00
subtitle: "Boolean Arithmetic - Toughest challenge so far"
image: ""
tags: ["learn", "course", "nand", "logic","gate", "ALU", "binary"]
---

> Background
>
> The centerpiece of the computer's architecture is the CPU, or Central Processing Unit, and the centerpiece of the CPU is the ALU, or Arithmetic-Logic Unit. In this project you will gradually build a set of chips, culminating in the construction of the ALU chip of the Hack computer. All the chips built in this project are standard, except for the ALU itself, which differs from one computer architecture to another.

### 1. The Theory

After finishing week 1 rather quick, i was eager to start week 2 and looking forward to next type of chips. The theory is presented in such an easy way that i can do arithmetic calculation base 2 and 10, negative numbers right away. Just to remember the sum part and carry part and you are good to go to project task. Here is the link to chapter 2  of the Elements of Computing Systems. [Link][2].

![pos-neg-number](https://user-images.githubusercontent.com/30904297/63788466-bdfaa500-c91f-11e9-8487-7accbd3e45d2.png)

There are only 5 hdl files to write and i can finish the first 4 at ease, which are Add16, FullAdder, HaflAdder and Inc16. However, the last is ALU (Arithmetic Logic Unit) turned out to be a toughest challenge so far. 

There are few reasons. First is that you need to turn to theory part to grap the idea how to distinguish the positive and negative base 16 (positive number has most significance bit 0, negative 1). Secondly, you need to absorb the abstraction idea of all elementary chips built in this and last week. That means you change your role from creator to user of the higher lever chips and revisit their documentations a few times. Actually, chips are used to build ALU are Mux16, Not16, Add16, And16 and Or8Way.

> Counting is the religion of this generation, its hope and salvation.
>
> -- Gertrude Stein (1874–1946)

### 2. The Project

![ALU](https://user-images.githubusercontent.com/30904297/63785718-fea3ef80-c91a-11e9-81ff-78a467119feb.png)

After many try and errors and google searches, i ended up with only almost 20 LOCs. It took 38 secs to run through all test cases and i was breathing a sight of relief that none failed case was found. Another small archievement was unlocked - a fully functional ALU chip, and i am happy now :tada:. Finally i found that the chip is quite simple but really powerful.

> Simplicity is the ultimate sophistication.
>
> -- Leonardo da Vinci

---

**Key concepts**: Binary numbers, binary addition, the two's complement method, half-adders, full-adders, n-bit adders, counters, Arithmetic Logic Unit (ALU), combinational logic.

[More information][project02]


[2]: https://drive.google.com/file/d/14XfZpXZtiHb6py8S1ZiOrHkHMSUCfA7t/view
[project02]: https://www.nand2tetris.org/project02