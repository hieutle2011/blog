---
title: "Vim Editor"
date: 2019-08-21T21:29:33+07:00
draft: false
tags: ["vim", "linux"]
---

Well, recently i often work with docker and control config on server, i suffered a lot due to my weakness regards vim usage on linux.

Turn out, these basic things prove significant as you'd like to pursue DevOps career.

It would be great to improve on my vim skill by taking note down the essential of this powerful editor. Moreover, there is one tutor right in your Ubuntu terminal.

Let's get started and hope you learn something. 

Go to your terminal and run below command, and voila you are in side vim tutor.

```shell
$ vimtutor
```

Be noticed! Button Esc is your friend, press it as many times as you wish to turn to Normal Mode and to quit vim, type:

```shell
# Be sure that you in Normal Mode by press Esc now
<ESC> :q <ENTER>
# or discard any change with
<ESC> :q! <ENTER>
# or save and quit (write and quit hence wq)
<ESC> :wq <ENTER>
```

These commands will be helpful to me and here is the quick reference.

### Navigate
* Moving the cursor with **k** up, **j** down, **h** left, **l** right. Try not to use normal navigator buttons.
* **e** to end of word
* **$** to end of line
* **0** to begin of line
* **G** to the bottom of file
* **gg** to the top of file
* **CTL-G** to show current location in the file
* Go to line 124 by type 124 then **G**

### Search
* **/** follow the phrase, **n** for next phrase, **N** the opposite
* **CTL-o** and **CTL-i** go back and forth from where you are
* **%** to find matching parentheses for debugging

### Insert Mode
##### Normal
* **i** Insert before cursor 
* **a** Insert after cursor
* Append with **A**

##### Replace until the end of word
* **ce** you enter --Insert-- mode
* **c$** change to the end of line

##### Open command
* **o** open a line below cursor
* **O** open a line above cursor

### Delete
* Delete character with **x**
* Delete a word with **dw**
* **d3w** to delete 3 words

##### Line
* **d$** to delete to the end of line 
* **dd** to delete whole line
* **2dd** to delete 2 whole lines

Note that we have 2 parts operator and motion (eg: d and w). By using count, we can repeat many time that motion:

* **2w** to 2 words fw
* **3e** to end of 3rd word fw

### Undo
* **u** to undo last command
* **U** to fix a whole line

### Select text
* **v** then move the cursor

### Copy
* **y** copy selected words
* **yw** copy the whole word

### Put or Paste
* **p** paste the copy/cut line

### Replace
* **rx** get to Insert Mode and replace one character *x*
* **R** get to Insert Mode and replace more than one character
* **:s/old/new/g** to **s**ubstitue *old* for *new*

### Execute external command
* **:!** follow by command. Eg: **:!ls** to list your directory

### Write file
* **:w filename**

These are more than enough for me now. Happy editing!
