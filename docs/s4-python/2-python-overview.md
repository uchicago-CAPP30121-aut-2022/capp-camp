---
layout: default
title: Python Overview
nav_order: 2
parent: Python Programming
---

# Python Overview

Python, named after the 1970s BBC comedy show "Monty Python's Flying Circus", has its origins in the Netherlands. In 1987, Dutch scientist Guido van Rossum began developing Python as a side project at the national research institute CWI and then released it to the public in 1991. Since then, the language has gone through several versions (the latest stable version being 3.10.6) and exploded in popularity. The latest [Stack Overflow Developer Survey](https://survey.stackoverflow.co/2022/#most-popular-technologies-language), conducted in May 2022 with over 70,000 respondents, indicated that Python was the fourth most popular technology behind JavaScript, HTML/CSS, and SQL. The TIOBE Index, a monthly indicator of programming popularity, reported in [August 2022](https://www.tiobe.com/tiobe-index/) that Python was the top language.

Your instructors for CAPP 30121 have chosen to use Python rather than another common language like Java, C, or C++ because it offers several advantages, such as greater readability. In addition, it is free, open-source, and general purpose; offers a rich and growing collection of libraries for data science and machine learning; and is currently used extensively within both academia and industry.

In this section, we will not attempt to teach Python. Rather, we will introduce some of its basic symbols and syntax to (a) give you a better understanding of the Python-specific features offered by VS Code and (b) allow you to practice writing Python expressions in the next exercise. Let's get started!

## Anatomy of a Python File

Your programming assignments will require you to edit Python files, which end in `.py`. These files will have a similar structure:

**Docstring**.  At the very top of the file, you will find a doc string that starts and ends with a series of three quotation marks. When you run your Python program, the contents of the doc string will be ignored. Doc strings are used for informational purposes, such as conveying the name of the program, its author, and a brief description.

'''
\'''
Epidemic modelling

Launa Greer

Functions for running a simple epidemiological simulation
\'''
'''

**Imports**:  Below the doc string, you will often find a series of one-line statements beginning with the word `import`. The `import` keyword allows your Python program to access logic from another Python program. The Python language has a standard library of Python programs, called _modules_, that can be imported. For example, in the code snippet below, the `random` module is being imported so the "Epidemic modelling" program can call it to generate pseudo-random numbers.

'''
\'''
Epidemic modelling

Launa Greer

Functions for running a simple epidemiological simulation
\'''


import random

import click
'''

**Logic**:  After the `import` statements, the main logic of the program begins. You've already seen `print` commands in previous lessons. Printing "Hello, Gustav!" to the terminal is a simple example of program logic.

## Example Data Types

Below are two of Python's built-in data types that we'll reference as we practice writing code. You will learn about these data types and others in more detail during CAPP 30121:

### Numerics: `int` (integer) and `float` (float)

Integers are whole numbers that can be positive or negative. Examples could include `-10`, `0`, `3`, or `49999`.

Integers can be added (`+`), subtracted (`-`), multipled (`*`), and raised to a power (`**`). They can be divided using either _true division_ (`/`) or _floor division_ (`//`). The latter only takes the whole number part and not the decimal part following a normal/true division operation. You can also calculate the modulo of two integers—i.e., their remainder following division—using `%`.

When applying several operations in sequence, normal order of operations is followed. Mathematical expressions in parentheses are evaluated first, followed by exponents, multiplication and division from left to right, and finally, addition and subtraction from left to right.

`float` represents floating-point numbers: numbers that have a decimal point. The same operations as integers apply. `3.45`, `-0.9`, and `2003.0` are all examples. The data type got its name from the fact that its decimal point can "float" to wherever it's needed based on how the data is stored in computer memory.

#### Checkpoint

In your terminal, type `ipython3` to launch an interactive Python shell where you can test Python commands.  Then run the following expressions to confirm their value. (Note: You don't need to type "In[1]" or "Out[1]"; those are examples of what you would see as output in the terminal.)

Order of Operations
```python
In [1]: ((4 - 5) + 3)**2
Out [1]: 4
```

Normal/True Division
```python
In [2]: 4 / 5
Out [2]: 0.8

In [3]: 4 // 0 # Division by zero will cause Python to throw an error
Out [3]: ---------------------------------------------------------
ZeroDivisionError       Traceback (most recent call last)
Input In [12], in <module>
----> 1 4 // 0

ZeroDivisionError: integer division or modulo by zero
```

Floor Division
```python
In [4]: 4 // 5
Out [4]: 0
```

Modulo
```python
In [5]: 4 % 5
Out [5]: 4

In [6]: 6 % 3
Out [6]: 0

In [7]: 5 % 4
Out [7]: 1
```

## Booleans: `bool`

Booleans are `True` and `False` values. You can use logical operators like `and`, `or`, and `not` to create boolean statements:

- `not` is a negation. For example, `not True` would yield `False`.

- `and` requires that both conditions on either side are `True`. `False and True` would therefore evaluate to `False`.

- `or` requres that one of the conditions are true. `False or True` would therefore evaluate to `True`.

You can also use comparison operators like equals (`==`), doesn't equal (`!==`), greater than (`>`), less than (`<`), greater than or equal to (`>=`), and less than or equal to (`<=`) to create booleans.  For example: `5 == 3` would output `False` and `(40 / 10) >= 10` would output `True`.

Like numeric types, parentheses will also dictate the order in which expressions are evaluated.


#### Checkpoint

In your terminal with `ipython3` running, test these additional commands:

```python
In [8]: not(not False)
Out [8]: False
```

```python
In [9]: not(False) or True
Out [9]: True
```
```python
In [10]: not(False or True)
Out [10]: False
```

```python
In [11]: 100 == 100
Out [11]: True
```

```python
In [11]: -10 < -9.99
Out [11]: True
```

## Variables

We have been generating Python expressions. The values aren't saved anywhere after Python has finished evaluating them. To save the result of an expression, we use variables.  You define the name for your variable, followed by an equal sign, and then the expression. For example:

```python
is_chicago_summer = True
summer_high_temp_f = 95 
summer_low_temp_=f = 40
```
As shown above, Python has certain expectations and conventions for variable names. 

- A variable name must start with a letter or underscore (`_`).

- A variable name can _only_ contain alphanumeric characters and underscores (`A-z`, `0-9`, and `_ `).

- Variable names are case-sensitive.

- Variable names use **snake case**, where all letters are lowercase and spaces are represented by underscores.

#### Checkpoint

In your terminal with `ipython3` running, practice creating a variable and printing its value using `print`. The variable will live in memory until the terminal is closed.

```python
In [12]: plancks_constant = 6.62607 * 10**-34

In [13]: print(plancks_constant)
6.62607e-34
```

```python
In [14]: 1_invalid_num = 200 # Invalid variable names will cause Python to throw a syntax error
Input In [14]
    1_invalid_num = 200
     ^
SyntaxError: invalid decimal literal
```

## Control Flow

Now that we have expressions and variables, we can begin writing statements that affect Python program's control flow, or the order in which it executes statements. For now, we will do this using conditional blocks.

### if-elif-else Blocks

Sometimes we only want to execute code if a condition is satisifed.  Python enables this functionality by providing `if`, `elif`, and `else` conditional statements.  For example:

```python
min_rider_height = 48
max_rider_height = 84
rider_height = 36

if rider_height < min_rider_height:
    print("Sorry, you must be at least", min_rider_height, "inches.")
elif rider_height > max_rider_height:
    print("Sorry, you can't be any taller than", max_rider_height, "inches.")
else:
    print("Sure, you can ride the roller coaster.")
```

If the first condition evaluated at `if` is `True`, Python will execute everything underneath that `if` statement (i.e., within the "if block") without evaluating the other conditions. The program will print out `Sorry, you must be at least 48 inches.`.

If the first condition evaluated at `if` is `False`, Python will move to evaluate `elif` ("else if") instead.  If that condition is `True`, that "elif block" will be run, and the program will print `Sorry, you can't be any taller than 84 inches.`. You can have as many `elif` blocks as you want between the initial `if` statement and the final `else` statement.

If all of the previous conditionals evaluate to `False`, then the `else` statement is executed.  Therefore, if you are greater than 36 inches and shorter than 84 inches, the program would print `Sure, you can ride the roller coaster.`.

It is important to emphasize here what the conditional block looks like. Each `if`, `elif`, and `else` statement ends with a colon (`:`) and the code underneath it is indented.  Python uses _indentation_ to indicate a block of code. Python permits you to use one or more spaces for indentation. The only requirement is that you use indentation consistently across your Python file.  In CAPP 30121, you will use four spaces to indent.

### Functions

The above example was contrived; what if we wanted to call the if-elif-else block repeatedly with different rider heights?  To accomplish this, you would use a `function`.  We won't go over functions in great detail now. In your first few assignments for CAPP 30121, you will be writing logic within functions that have already been created for you.  At this moment, it is just helpful to understand that a function receives inputs called "arguments" and then performs operations on those arguments to return output.Functions are called from other places in a Python file or may be used in a different file altogether.

For example, if we wanted to write a function for our conditional block, it would look something like this:


```python
def assess_rider_height(rider_height):
    """
    Prints a message to the terminal
    summarizing whether the given height
    permits the rider to go on 
    a roller coaster.

    Inputs:
        rider_height (int): The rider
            height in inches.

    Returns:
        None    
    """
    min_rider_height = 48
    max_rider_height = 84

    if rider_height < min_rider_height:
        print("Sorry, you're not tall enough to ride.")
    elif rider_height > max_rider_height:
        print("Sorry, you're too tall for this ride.")
    else:
        print("Sure, you can ride the roller coaster.")
```

And then we would call it later in our Python script like this:

```
assess_rider_height(20)
assess_rider_height(68)
assess_rider_height(90)
```

A function starts with the keyword `def` followed by the function name (here, `assess_rider_height`) and a pair of parentheses.  Inside the parentheses, you can define what inputs are accepted. Here, `rider_height` is accepted. When you call function farther down the script with `assess_rider_height(20)`, the value `20` is passed in for the `rider_height`. Then the rest of the statements are evaluated and the correct `print` command is made.  In this case, the function doesn't explicitly return any value using the `return` keyword, so the `return` value is understood to be the Python value `None`.

Note also the presence of a function docstring, defined by two sets of triple quotation marks (`"""`). Like a file docstring, function doc strings provide helpful information to other programmers. Function doc strings commonly summarize what the function does, what inputs are accepted, and what value (or values) will be returned.

To provide a simple, second example:

```python
def square(n):
    """
    Squares an integer.

    Inputs:
        n (int): The integer.

    Returns (int): The result.
    """
    return (n)**2


print(square(3)) # Will print 9
print(square(-4)) # Will print 16
```

The above function is declared again using the keyword `def` and given the name `square`. Square takes an integer `n` as input and then returns that integer raised to the second power. Here we see an explicit `return` statement that will return the integer result.

#### Checkpoint

Copy and paste the function into the terminal. Press Enter (Return) until `ipython3` recognizes that you are done entering input. Then try calling the function as shown above.


## Next Steps

Even with this small sample of Python's available data types and control flow mechanisms, we can compose complex programs! You will learn more about how VS Code helps with Python programming and gain practice writing Python expressions in the next section.