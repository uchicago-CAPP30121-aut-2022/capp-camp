---
layout: default
title: Run Python Programs
nav_order: 5
parent: Introduction to Linux
---

# Run Python Programs

In this section, you will walk through the steps to edit and run a Python program.

## Use an Editor

Let's start by editing a text file. List the files in the `lab1` directory. You should see the following:

```
backups hello_world.py  my_echo.py  my-input.txt  test.txt
```

How do we view and edit the contents of these files? There are many high-quality text editors for Linux. We will use Visual Studio Code, which is good for writing code.

You can open a specific file, say `test.txt`, using the `code` command from the Linux command-line by typing:

```
code test.txt
```

Specifically, you’ll see the following text:

```
Lab 1 Test file
===============

Author: Firstname Lastname
```

If the file is blank, close it and ensure that `test.txt` exists in your local directory (use `ls` to list the files in your local directory). If it does not, use `cd` to navigate to the `lab1` subdirectory inside the `lab1_linux_remote` directory.

For now, we will use VS Code in a very basic way. You can navigate to a particular place in a file using the arrow keys (or your mouse) and then type typical characters and delete them as you would in a regular text editor. You can save your changes using the `save` option in the file menu or use the keyboard shortcut `Crtl-s`.

### Checkpoint

1. Add your name after `Author:` in this file.

2. Save the file.

3. Close and reopen the file, ensuring that your name is still there.

## Run a Python Program

|   |   |
|---|---|
|`python3 file.py`|Runs the Python program `file.py`.|

In CAPP 30121, you will learn Python. To run a Python program, use the command `python3` and the name of the file that contains your program.

Use `ls` to verify there is a file named `hello_world.py` in your `lab1` directory. Now, run the program in `hello_world.py` by typing:

```python
python3 hello_world.py
```

This program is very simple. It just prints “Hello, World!” to the screen.

## Exercises

In this section you will modify and re-run the program in `hello_world.py`. This change is very simple but goes through all the mechanical steps needed to program.

Open the file `hello_world.py` with the command:

```bash
code hello_world.py
```

The file contains a single line of code:

```python
print("Hello, World!")
```

Change this line so that it instead says "Hello, " and then your name. For example if your name were Gustav Larsson, the line would read:

```python
print("Hello, Gustav!")
```

Once you are finished with your edits, save the file and rerun the program using `python3`. Confirm that "Hello, " followed by your name and an explanation point, are printed in the terminal.

--

Let’s recap the steps to programming in Python with the terminal:

1. Change your `.py` file with an editor.

2. Save the file.

3. Run the file with `python3`.

Forgetting to save the file (step 2) is a _very_ common mistake!

In addition to the command-line version of Python, programmers often use Jupyter notebooks and other interactive versions of Python. You will be using `ipython3`, an interactive version of the Python interpreter, later in CAPP 30121.

{:style="text-align:center"}
[Previous](./4-man-pages.html){: .btn } [Next](./6-io-streams.html){: .btn }
