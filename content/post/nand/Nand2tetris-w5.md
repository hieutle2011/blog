---
title: "Nand2tetris W5"
author: ""
type: ""
date: 2019-09-29T10:26:08+07:00
subtitle: "Computer architecture"
image: ""
tags: ["learn", "course", "nand", "computer", "architecture", "Neumann", "CPU"]
draft: false
---

Last week, my wife came to BKK to see me and we had a wonderful short trip to Koh Lan island just 40 minutes away from Pattaya. It had been almost 2 months since we last met when i was in Vietnam back then, so that we did enjoyed our time together. Moreover, we accompanied by 2 great friends in Son and Tik and all of us laughed a lot in that sea food restaurant playing games and drinking beers.

That is the reason why i was late for week 5 project until today. To be fair, this project of building a computer is most challenging since beginning of the course. I found that i am not the only one got stuck at some point building the CPU in a forum specialized to the nand2tetris. Surfing through all the related posts and reading answers did give me more insights of the CPU and kept me going through.

This week material is quite overwhelm to me, 92 minutes of videos, 92 pages of slides and 29 pages of book chapter for me to work on. What all the 9s and 2s have to do are really funny i guess. Also i need to go back to previous chapter 4 (machine language) to review the logic behind jump field of C-instruction. It was huge and i would easily forget all those details after commencing the course, so that i believe these below notes will help my future me to understand what was going on.

### Computer architecture fundamentals

The chapter starts with the idea of The Stored Program Concept which was formed in 1930s. That is a computer with finite hardware platform can perform infinite number of tasks from instructions passed to it. These instructions can be combined in building block that yeild arbitrarily sophisicated programs, and these programs are not fixed with the hardware but be stored in memory just like data, called software. Such that different loaded softwares ask the hardware to perform differently.

As you can see from below diagram, the von Neumann machine (1945) is the practical architecture and almost all mordern computers are based on this concept.

![The von Neumann architecture](/images/vonNeumann.png)

### The Hack hardware platform

The Hack platform is a 16-bit von Neumann machine, designed to execute programs written in Hack machine language (chapter 4). The Hack platform consists of a CPU, 2 seperate memory modules playing the roles of instruction memory (ROM) and data memory (RAM), and 2 memory-mapped I/O devices: a screen and a keyboard.

The ROM contains the the 16bit instruction: “<span style="color:black">i</span>xx<span style="color:blue">a</span><span style="color:blue">cccccc</span><span style="color:green">ddd</span><span style="color:brown">jjj</span>” where:

* `i`-bit: operation code. If opcode=0 means A-instruction, the whole 16bit is value of the constant should be loaded into the A register. Else, opcode=1 mean C-instruction, the breakdown is as below:

* `a` and `c`-bit: comparision part

* `d`-bit: destination part

* `j`-bit: jump part (have to dig deep for the logic in week 4 material!)

Because the pre-loaded ROM is provided, all hard work is to write hdl code to build the data memory and the CPU. While the data memory has 3 parts: RAM16K, Screen and Keyboard memory-mapped, which is fairly straightforward, i found CPU is a real killer. It took me hours of reading on course material and on forum for CPU, figuring out the control part of every chip, debugging on each line of the test script and finally grasp the idea of the instructor. I did ask on the forum for someone to look at my CPU code, but before receiving any feedback, i could pass the test successfully myself.

![CPU diagram](/images/CPU.png)

Then building the Hack computer is a peice of cake as all i need to do is connect 3 parts together in just a few minutes. That's it!

![Hack computer](/images/Hack.png)

---

**Key concepts:** Von Neumann and Harvard architectures, the stored program concept, fetch-execute cycle, data bus, instruction bus, CPU, computer design.

- [Slide][slide]

- [Reading][chapter5]

- [Forum][forum]

[slide]: https://docs.wixstatic.com/ugd/56440f_96cbb9c6b8b84760a04c369453b62908.pdf
[chapter5]: https://docs.wixstatic.com/ugd/44046b_552ed0898d5d491aabafd8a768a87c6f.pdf
[formu]: http://nand2tetris-questions-and-answers-forum.32033.n3.nabble.com/Project-5-f32606.html