---
layout: default
title: Wild Cards
nav_order: 4
parent: Introduction to Linux
---

# Wild Cards (Using an Asterisk)

Sometimes when we enter a string, we want part of it to be variable, or a wildcard. A common task is to list all files that end with a given extension, such as `.txt`. The wildcard functionality, through an asterisk, allows us to simply say:

```bash
$ ls *.txt
```

The wildcard can represent a string of any length consisting of any characters - including the empty string.

It is important to be **careful** using wildcards, especially for commands like `rm` that cannot be undone. A command like:

```bash
$ rm *   ### DO NOT RUN THIS COMMAND!
```

will delete **all** of the files in your working directory!

FYI, the text that follows a # on the Linux command-line is assumed to be a comment and is ignored.

### Exercises

Navigate to your `camp_camp` directory. What do you see when you run `ls pa*`? What about `ls pa*/*`?

What do you expect to see when you run the command `ls ../pa*` from within your `camp_camp/lab1 directory`?
