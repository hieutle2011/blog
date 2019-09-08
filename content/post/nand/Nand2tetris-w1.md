---
title: "Nand2tetris Week1"
author: ""
type: ""
date: 2019-08-25T10:01:17+07:00
subtitle: "Primitive Nand gate"
image: ""
tags: ["learn", "course", "nand", "logic","gate"]
---

> Background
>
> A typical computer architecture is based on a set of elementary logic gates like And, Or, Mux, etc., as well as their bit-wise versions And16, Or16, Mux16, etc. (assuming a 16-bit machine). This project engages you in the construction of a typical set of basic logic gates. These gates form the elementary building blocks from which more complex chips will be later constructed.

Here is what i have learnt in this week.

### 1.Boolean laws

![Boolean-Identities](https://user-images.githubusercontent.com/30904297/63658581-deb6e380-c7d5-11e9-9141-a1b093c92b09.png)

Any boolean function can be represented using an expression containing only **NAND** operations.

##### Proof:

- NOT(x) = (x NAND x)

- (x AND y) = NOT(x NAND y)

### 2.Hardware description language

> In computer engineering, a hardware description language is a specialized computer language used to describe the structure and behavior of electronic circuits, and most commonly, digital logic circuits.
> [Wikipedia][2]

Here is the `hdl` code for the **And gate** (or chip).

```shell
/**
 * And gate: 
 * out = 1 if (a == 1 and b == 1)
 *       0 otherwise
 */

CHIP And {
    IN a, b;
    OUT out;

    PARTS:
    Nand(a=a,b=b,out=o);
    Not(in=o,out=out);
}
```

Notice how **And gate** is built on **Nand gate**, ... and **Not gate**, but actually **Not gate** is built on **Nand gate** as well. **Nand** is the atom gate, hence the course named *Nand2Tetris*.

Premitive **Nand gate** that be used to build other gates. **Nand** means not-And, the opposite of **And gate**.

x  | y |Nand|   |And
---|---|--- |---|---
0  | 0 | 1  |   |0
0  | 1 | 1  |   |0
1  | 0 | 1  |   |0
1  | 1 | 0  |   |1

### 3.Project: Logic gates

Enough for the theory, let's get your hand dirty writing actual hdl codes. In this week, 15 gates are built can be categorized into 3 groups:

- Elementary logic gates (e.g: And, Or, Xor, ...)

- 16-bit variant of above gates (e.g: And16, Or16, ...)

- Multi-way variants gates






Reference

* [Study group notes][1]
* [Survival Guide][3]
* [Answer sample][4]
* [Appendix A:  Hardware Description Language (HDL)][5]


[1]: https://github.com/LearnTeachCode/nand2tetris
[2]: https://en.wikipedia.org/wiki/Hardware_description_language
[3]: https://www.nand2tetris.org/software/HDL-Survival-Guide.htm
[4]: https://github.com/jcoglan/nand2tetris/tree/master/projects/01
[5]: https://docs.wixstatic.com/ugd/44046b_2cc5aac034ae49f4bf1650a3d31df32c.pdf