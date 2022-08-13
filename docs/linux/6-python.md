---
layout: default
title: Running Python Programs
nav_order: 6
parent: Introduction to Linux
---

# Editing and Running a Python Program

In this section, you will walk through the steps to edit and run a Python program. We’ll start with editing a text file.

### Using an Editor

List the files in the `lab1` directory. You should see the following:

```
backups hello_world.py  my_echo.py  my-input.txt  test.txt
```

How do we view and edit the contents of these files? There are many high-quality text editors for Linux. We will use Visual Studio Code, which is good for writing code.

You can open a specific file, say `test.txt`, using the code command from the Linux command-line by typing:

```
code test.txt
```

Specifically, you’ll see the following text:

```
Lab 1 Test file
===============

Author: Firstname Lastname
```

If the file is blank, quit `code` and ensure that the file `test.txt` exists in your local directory (use `ls` to list the files in your local directory). If it does not, use `cd` to navigate to the `lab1` subdirectory inside the `lab1_linux_remote` directory.

Note: somewhat counterintuitively, the menu bar for Visual Studio Code is at the top of the Browser window. You need to run your mouse over the name to see the menu options.

For now, we will use Visual Studio Code (`code`) in a very basic way. You can navigate to a particular place in a file using the arrow keys (or your mouse) and then type typical characters and delete them as you would in a regular text editor. You can save your changes using the `save` option in the file menu or use the keyboard shortcut `Crtl-s`. To quit, you can use the file menu `quit` option or the keyboard shortcut `Ctrl-q`.

As an aside, you can also launch code from the application launcher: simply click the Application button (at the top left of your screen), type “code” in the input box, and then click on the Visual Studio Code icon. You can then use the `file` menu to navigate the correct file. As with the terminal application, you might want to pin the icon for launching Visual Studio Code to your launch bar (right click your mouse and choose the “Lock to Launcher” menu item.)

#### Exercises

1. Add your name after `Author:` in this file.

2. Save the file.

3. Close and reopen the file in `code`, ensuring that your name is still there.

4. Finally, close `code`.

## Run a Python Program

|   |   |
|---|---|
|`python3 file.py`|Runs the Python program `file.py`.|

In this class, you will learn Python. To run a Python program, use the command python3 and the name of the file that contains your program.

Use `ls` to verify that there there is a file named `hello_world.py` in your `lab1` directory. Now, run the program in `hello_world.py` by typing (don’t forget about auto-complete!):

```python
python3 hello_world.py
```

This program is a very simple. It just prints “Hello, World!” to the screen.

#### Exercises

In this section you will modify and rerun the program in `hello_world.py`. This change is very simple but goes through all the mechanical steps needed to program.

Open the file `hello_world.py` with the command:

```bash
code hello_world.py
```

The file contains a single line of code:

```python
print("Hello, World!")
```

Change this line so that it instead says “Hello, ” and then your name. For example if your name were Gustav Larsson, the line would read:

```python
print("Hello, Gustav!")
```

Do the following steps:

1. Save the file `hello_world.py` in Visual Studio Code (forgetting to save is a surprisingly common error).

2. Rerun the program using `python3`.

Let’s reinforce the steps to programming in Python with the terminal:

1. Change your `.py` file with an editor.

2. Save the file.

3. Run the file with `python3`.

Forgetting to save the file (step 2) is a very common mistake!

In addition to the command-line version of Python, programmers often use Jupyter notebooks and other interactive versions of Python. We will be using `ipython3`, an interactive version of the Python interpreter, in this course. We’ll introduce it during the first week of the quarter.
