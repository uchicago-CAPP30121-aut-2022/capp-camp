---
layout: default
title: Shortcuts
nav_order: 7
parent: Introduction to Linux
---

# Shortcuts

Used at the Linux prompt, the keyboard shortcut `Ctrl-P` will roll back to the previous command. If you type `Ctrl-P` twice, you will roll back by two commands. If you type `Ctrl-P` too many times, you can use `Ctrl-N` to move forward. You can also use the arrow keys: up for previous (backward), down for next (forward).

Here are few more useful shortcuts:

- `Ctrl-A` will move you to the beginning of a line.

- `Ctrl-E` will move you to the end of a line.

- `Ctrl-U` will erase everything from where you are in a line back to the beginning.

- `Ctrl-K` will erase everything from where you are to the end of the line.

- `Ctrl-L` will clear the text from current terminal

As a caveat, Visual Studio Code's own preconfigured keyboard shortcuts frequently interfere with these commands.  To work around this:

1.  Navigate to “File > Preferences > Settings”.  
          
2.  Click on the “User” tab and then search for “allowChords”.  
    
3.  Uncheck the box for the option when it appears.

Afterwards, play around with these commands. Being able to scroll back to, edit, and then re-run previously used commands saves time and typing! And like auto-completion, getting in the habit of using keyboard shortcuts will reduce frustration as well save time.

### Running Commands Sequentially

It is often convenient to chain together commands that you want to run in sequence. For example, recall that to print the working directory and list all of the files and directories contained inside, you would use the following commands:

```bash
$ pwd
/home/username/
$ ls
Desktop  Documents  Downloads  Music  Pictures  Public  Templates  Videos
```

You could also run them together, like so:

```bash
$ pwd ; ls
/home/username/
Desktop  Documents  Downloads  Music  Pictures  Public  Templates  Videos
```

First, `pwd` is executed and run to completion, and then ls is executed and run to completion. The two examples above are thus equivalent, but the ability to run multiple commands together is a small convenience that could save you some time if there is a group of commands that you want to execute sequentially.
