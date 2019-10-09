---
title: "Nand2tetris W6"
author: ""
type: ""
date: 2019-10-09T20:23:12+07:00
subtitle: "Write an assembler"
image: ""
tags: ["learn", "course", "nand", "python", "assembler"]
draft: true
---

This week marks the end of building hardware parts and the beginning of the computer software hierarchy. Each computer has a binary machine language, including a number of 0's and 1's, and a symbolic machine language, consisting of human-friendly mnemonics. Both languages serve the same purpose and are completely equivalent.

However, assembly language is far easier for human to write and understand. To enjoy this benefit, it is required for a assembler to translate the symbols and labels into binary machine code. The assembler can  be carried out either by using paper and pen, or by using a high level language.

For example, with agree-upon syntax, one instruction is documented as **LOAD R3, 7** rather than a mysterious **110000101000000110000000000000111**.

I decided to implement the assembler with the latter way with Python. Although i have been working with Javascript, Dart and Go recently, Python syntax is by far the simplest and is most suitable for such a quick solution. It turns out they recently add some type safe in Python which is more than welcomed.

The translation is mostly string manipulation, so that i use regex pattern to parse the instruction. Unittests are written to help me test the object methods and functions, otherwise i would be in serious trouble without them. My assembler implementation can be accessed [here][assembler], and the final result look like this.

![Assembly example](/images/assembly.png)

---

**Key concepts:** Binary and symbolic machine languages, parsing, symbol tables, code generation, cross assembler, assembler implementation.

- [Slide][slide]

- [Reading][chapter6]

[slide]: https://docs.wixstatic.com/ugd/56440f_65a2d8eef0ed4e0ea2471030206269b5.pdf
[chapter6]: https://docs.wixstatic.com/ugd/44046b_89a8e226476741a3b7c5204575b8a0b2.pdf
[assembler]: https://github.com/hieutle2011/nand2tetris/tree/master/assembler